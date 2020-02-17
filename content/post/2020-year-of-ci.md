---
author: Dave Simpson
date: 2020-02-17T00:05:55Z
publishDate: 2020-02-17T00:05:55Z
draft: false
title: '2020 - Year of CI (not VDI)'
description: ""
categories:
- Posts
tags: [blog]
thumbnail: "img/circleci.png"
---
When I last had a serious update of this site it was 2017 and I had decided to go all trendy, with my static site generator and my S3 hosted website. But I didn't really finish the job, so this time, whilst revisiting my blog as part of a Toastmasters project to write eight blog posts in a month, it was time to close the Circle(CI). Haha!
Yes, these February 2020 blog posts are more intertwined than one might first think.

## What was missing? ##
Previously, I was using a version of Hugo which created your site locally, but then you had to work out another means by which to get it uploaded somewhere, so once I'd pushed content to Github, I was left with the task of uploading new content to the S3 bucket, which was a bit tedious. I was gonna finish this off, but I got distracted by something else shiny and never came back to it, until now!

## New Year, New Hugo ##
There'd been some significant advancements to Hugo whilst I had "been away" so I discovered that now I could use the new hugo deploy feature to throw everything at S3 and invalidate pages in CloudFront, which was an immediate win. You can do a WhatIf on this as well, which was handy!
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

This meant that I could do everything from Powershell,  but there was one massive drawback, this didn't allow me to upload any content to be published at a future time, which could be a bit of a problem! 