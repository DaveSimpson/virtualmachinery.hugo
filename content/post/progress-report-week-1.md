---
author: Dave Simpson
date: 2017-08-29T14:59:39+01:00
draft: false
title: 'Progress Report Week 1'
description: "Progress made moving my website to a static site"
categories:
- Posts
tags: [blog]
thumbnail: "img/"
---

It's been about a week since I decided to shift my site from Blogger to using static pages hosted on AWS with Hugo as the means to develop it. In that time, I've
- started writing pages using markdown, I'd never used it before
- finally got to grips with Git to track all my changes locally (I also have the option to put my code in github / AWS)
- converted all my web pages to markdown, from blogger, via wordpress
- changed image locations
- added a new #LonVMUG based blogroll
- incorporated the bits for disqus and google analytics

The whole point of this exercise was to put myself on the bottom of a different learning curve and that has definitely worked. Infrastructure Engineers such as myself definitely need to pick up more coding skills, so it is probably well past the time that I should handle things like Git which have always been "for those developers, not us". The basics of Git are real easy, once you understand the basics you're all good. There's not a whole bunch of commands and other people have already documented the basics, but I might do that too, if there's time or demand, as if nothing else, a quick crib sheet works wonders. I generally learn best by doing or writing, if it's gone in my eyes, it has to go through my brain to get out of my hands through the keyboard or pen, so hopefully some of it sticks!

So just in time for VMworld, I had a new blog location, a new look, the basics in place. Grand.

This all sounds great, but is it? I can make a change to my site locally and see it instantly, I can run draft pages locally and know they don't end up online until I am ready, the hugo web server updates on the fly and a new site build takes a second or so. Locally, on my C drive, where none can see it. Then the content still needs to go up to S3 and given that a small change such as a single tag or adding a new page has a domino effect on the rest of the site content, it takes a lot longer than that 1 second to get the new content up into S3. This means that there's still quite a lot more to do:

- Git needs to go to GitHub / AWS CodeDeploy
- Transfer the domain to AWS (?)
- Need SSL certs / CloudFront configured
- Have to build the CI/CD pipeline

I had a first attempt at being really clever as I have an S3 bucket with the hugo content in it and the usual buckets for serving up the website from S3. It should be possible to use a Lambda function to trigger when there is a change to the "source" bucket, be that an add or a delete and run a Lambda function to generate the new site code with hugo. My first attempt didn't work, so I will have to try this again when I've got a bit more time to think about it. 

Having CloudFront in place would mean that the content was cached and that might make more sense given that there's then less reliance on the S3 bucket and I can swap content in and out of that without worrying about it. Seems like the next thing to do.