---
author: Dave Simpson
date: 2020-02-17T00:05:55Z
publishDate: 2020-02-17T09:05:55Z
draft: false
title: '2020 - The Year of CI (not VDI)'
description: "Adding CI to my static website"
categories:
- Posts
tags: [blog]
thumbnail: "img/circleci.png"
---
When I last had a serious update of this site it was 2017 and I had decided to go all trendy, with my static site generator and my S3 hosted website. But I didn't really finish the job, so this time, whilst revisiting my blog as part of a Level 4 [Toastmasters project](https://www.toastmasters.org/pathways-overview/pathways-persuasive-influence-path) to write eight blog posts in a month, it was time to close the Circle(CI). Haha!
Yes, these February 2020 blog posts are more intertwined than one might first think.

## What was missing? ##
Previously, I was using a version of the [Hugo](https://gohugo.io/) Static Site Generator which created your site locally, but then you had to work out another means by which to get it uploaded somewhere, so once I'd pushed content to [Github](https://github.com/), I was left with the task of uploading new content to the S3 bucket, which was a bit tedious. I was gonna finish this off, but I got distracted by something else shiny and never came back to it, until now!

## New Year, New Hugo ##
There'd been some significant advancements to Hugo whilst I had "been away" so I discovered that now I could use the new `hugo deploy` command to throw everything at S3 and invalidate pages in CloudFront, which was an immediate win. You can do a WhatIf on this as well, which was handy!
`hugo deploy --dryRun`

All I'd had to do to make this work was append a bunch of lines to my config.toml file;

```js
[deployment]

		# Files that match the regular expressions in the "Order" list will be uploaded first, in the listed order.
		order = [".jpg$", ".gif$", ".png$"]

[[deployment.targets]]
		name = "SOME_NAME_HERE"
		# S3; see https://gocloud.dev/howto/blob/#s3
		URL = "s3://BUCKET_NAME?region=eu-west-2"
		cloudFrontDistributionID = "DISTRIBUTION_ID"

# [[deployment.matchers]] configure behavior for files that match the Pattern.
[[deployment.matchers]]
		#  Cache static assets for 1 year.
		pattern = "^.+\\.(js|css|svg|ttf)$"
		cacheControl = "max-age=31536000, no-transform, public"
		gzip = true

[[deployment.matchers]]
		pattern = "^.+\\.(png|jpg)$"
		cacheControl = "max-age=31536000, no-transform, public"
		gzip = false

[[deployment.matchers]]
		pattern = "^.+\\.(html|xml|json)$"
		gzip = true
```

This meant that I could do everything from Powershell,  but there was one massive drawback, this only generated the site when I triggered that process. It didn't allow me to upload any content to be published at a future time, which could be a bit of a problem! 

## Enter CircleCI ##
The solution to my problem was to go fully CI, so what I needed was some way to rebuild my site, ideally in two seperate situations;

1. whenever I update it.
2. On a schedule, so content will drop when I want, without me having to intervene.

[CircleCI](https://circleci.com/blog/automate-your-static-site-deployment-with-circleci/) allows you to do both of these things relatively easily, assuming that you have a GitHub repo or similar. Sign up, link CircleCi to your GitHub account, setup a bit of config and you're good to go. The link above to one of their blog posts will walk you through things. Here's the config I'm using if this helps you get started;

```js
version: 2
jobs:
  build:
    docker:
        - image: cibuilds/hugo:0.56
    working_directory: ~/project
    steps:
      - checkout
      - run: git submodule sync
      - run: git submodule update --init
      - run:
          name: "Installing aws"
          command: |
              # TODO Should have these setup correctly as (cached) dependencies
              apk add --update py-pip python-dev
              pip install awscli --upgrade --user
      - run:
          name: "Run Hugo"
          command: hugo -v 
#      - run:
#          name: "Test Website"
#          command: htmlproofer /root/project/public --allow-hash-href --check-html --empty-alt-ignore --disable-external
      - deploy:
          command: |
              if [ "${CIRCLE_BRANCH}" == "master" ]; then
                  # Copy over pages - not static js/img/css/downloads
                  ~/.local/bin/aws s3 sync --acl "public-read" --sse "AES256" public/ s3://BUCKET_NAME/ --exclude 'img' --exclude 'post'
                  # Ensure static files are set to cache forever - cache for a month --cache-control "max-age=2592000"
                  ~/.local/bin/aws s3 sync --cache-control "max-age=2592000" --acl "public-read" --sse "AES256" public/img/ s3://BUCKET_NAME/img/
                  ~/.local/bin/aws s3 sync --cache-control "max-age=2592000" --acl "public-read" --sse "AES256" public/css/ s3://BUCKET_NAME/css/
                  ~/.local/bin/aws s3 sync --cache-control "max-age=2592000" --acl "public-read" --sse "AES256" public/js/ s3://BUCKET_NAME/js/
                  # Invalidate landing page
                  ~/.local/bin/aws cloudfront create-invalidation --distribution-id DISTRIBUTION_ID --paths /index.html / /page/* /post/*
              fi
              
workflows:
  version: 2
  commit-workflow:
    jobs:
      - build 
  scheduled-workflow:
    triggers:
      - schedule:
          cron: "0 10,20 * * *"
          filters:
            branches:
              only: master

    jobs:
      - build
```

Just add in your own `BUCKET_NAME` and `DISTRIBUTION_ID` and away you go. The blog post advises you where to add your S3 key/secret files, but when you get there, the location warns you that it doesn't work like that any more, well, it does!

You can watch the workflows progress when you change your code, this config is relatively simple and does the following, in a function called "build";

- Fires up a container that has Hugo installed
- Grabs your site from GitHub
- Installs AWSCLI
- Runs Hugo
- Uploads the publc files to S3, CloudFront aware
- Invalidates CloudFront

The container is up for about a minute, the CloudFront piece takes a little longer. 

The Workflows section shows that I have the "build" job ready to run every time I commit-workflow and also on a cron trigger, at 10AM and 8PM Zulu time. 

This site that you're reading now gets rebuilt a couple of times a day, plus anytime I push to GitHub.
