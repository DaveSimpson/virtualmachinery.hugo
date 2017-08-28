---
author: Dave Simpson
date: 2017-08-23 20:23:00+00:00
draft: false
title: 'Shipping a blog from Blogger to Hugo'
type: post
categories:
- Posts
description: "Trials and tribulations of moving a blog site from Blogger to Hugo (via wordpress!)"
thumbnail: "img/20170823hugohex.png"
tags: [blog]
---

This move was actually the culmination of a number of factors. The Blogger platform itself is fine, albeit proprietary and somewhat limited because of that, but you still need a bunch of other things to make that work. As with anything on the internet and I've sometimes had issues with the other aspects there. More than that though, this was simply a means to get myself into a newer format and learn something new along the way.

I chose Hugo because everyone else is doing it. Or so it seems. In addition, why would I move from Blogger to WordPress when I'd be migrating to a platform that sees sites get compromised, still has some limitations around content and so on. So switching up to using markdown appeared to be the way to go and from everything I read, Hugo is *really* fast.

## Installation

I figure that it will be easier to get all the installation stuff done upfront, so here we go, straight in...

To install Hugo itself, simply follow the process outlined in the [Hugo Quickstart guide](https://gohugo.io/getting-started/quick-start/ "Hugo qsg") which definitely will explain better than I. That site also has little video clips and the like to help you get started. 

The trickier part for me was that I needed to get my content out of Blogger to convert all that html into markdown. A quick bit of research on the hugo site led me to the [Migrate to Hugo](https://gohugo.io/tools/migrations/ "how to Migrate content to Hugo") page which explains how to get your content into hugo from a number of sources (incuding blogger). For most of this, you need python. I'm a Windows guy, but am not averse to a bit of command-line action, so Installing python and the associated prerequisites was pretty simple. I fell foul of some issues later on in that I initially installed [python 3.6](https://www.python.org/downloads/release/python-362/ "get python 3.6.2") and subsequently discovered that I also needed [python 2.7](https://www.python.org/downloads/release/python-2713/ "Get python 2.7"), so it could be worth getting both of those upfront.

You also need to install pip, the python package installer. Download [get-pip.py](https://bootstrap.pypa.io/get-pip.py "Download a script and run it - yeah, I know!") to a folder on your computer. Open a command prompt window and navigate to the folder containing get-pip.py. Then run python get-pip.py. 

Once you have pip, you can use that to install some other stuff afterwards. I know this was initially about exporting from blogger, but I ended up installing [Exitwp](https://github.com/thomasf/exitwp "Exitwp on github") to get things done. The documentation there shows you how this is done, it uses pip to parse all the requirements from a file and install them for you. Simple!

I also installed [MarkdownPad 2](http://markdownpad.com/download.html "MarkdownPad 2") to use later as a markdown file editor as it also has a web preview display function to show you what you're making - and then also had to install the [awesomium SDK](http://markdownpad.com/download/awesomium_v1.6.6_sdk_win.exe "Awesomium SDK") to stop the preview pane crashing.

## Exporting content
To get the content out of Blogger, you simply back it up. 

[![blogger backup](/img/20170823bloggersettings.png)] (/img/20170823bloggersettings.png)

As mentioned above, it turned out that I had issues with the plugin to handle the xml content that you export out of blogger, but I was able to easily import that xml file into wordpress.com within the free tier and then immediately export all of that content back out again as another xml file which I then knew was 100% sourced from WordPress. There are plugins that can do this, but plugins don't work on the free tier. I figure that most people moving to a static site will be exporting from WordPress anyway, so this makes the content here more relevant. 

In all honestly, I'm not 100% sure if that additional import/export through WordPress step was required or not, but it worked for me! From here, I basically followed the steps outlined by [Samuel Santos](https://samaxes.com/2016/02/static-site-from-wordpress-to-hugo/ "static site from wordpress to hugo") to do the export and conversion, which included using Exitwp as he recommended - you should already have this installed if you've worked through this post. As long as you have python 2.7 then the Exitwp script works. It does **not** work with 3.x. 

I then had a whole bunch of markdown files created for me, which I had to rename to *.md afterwards. This became the basis of my new site and would go into the posts folder within my local hugo setup for now. All the image links still pointed out to the wordpress site and I'd not done anything about comments at this point. As I'd want to fo some general editing of the web pages, then I'd probably be going through each one and could dowload the images on the way, but you could easily script a find and replace on a bunch of files to change the markdown code from using a remote site to using the local file repo. Secondly, my blog doesn't have that many (useful) comments so that's no big deal. At some point soon I will look into [Disqus](https://disqus.com/features/engage/ "Disqus site") to deal with that.

You will need to install a template to display the site how you'd like it. You'll have to pick one you like, I'm not gonna attempt to tell you what to pick here, there's plenty out there (or you can learn how to code your own, of course). The good thing about this is that there's plenty of example code around so you can see how the templates work by launching the a site. You can still follow the [Hugo Quickstart guide](https://gohugo.io/getting-started/quick-start/ "Hugo qsg") for help with this.

To see what is going on, you can run Hugo locally. This is as simple as firing up a command prompt from your local site folder where you will have a config.toml file and  and typing this:

    hugo server -D

You'll get instructions on where to go to see your local site. Generally this is http://localhost:1313/

Mess around with some content, learn the basics of your config.toml file and then you will want to create new content. Another command prompt will do, same location, type:

    hugo new posts/my-first-post.md

Or whatever you want your blog entry to be called. You'll see that hugo updates to show your content. Nice. Once you have this done, it's time to edit what you have with MarkdownPad 2. Again, you'll see updates in both the preview pane of your editor and on your site itself, whcih will make getting to grips with hugo easier. As you save content, watch the command prompt where hugo is running and you can watch it update and you'll see any error messages there that will point you to any syntax errors etc. 

At this point hopefully you're on your way. There's a lot more to it and I know I have more to learn, but this is a good starting point. Now to tidy up some posts before I start working out a cool CI/CD means of getting this new form of my content online. 



Some fun facts about [Hugo](http://gohugo.io/):

* Built in [Go](http://golang.org/)
* Loosely inspired by [Jekyll](http://jekyllrb.com/)
* Primarily developed by [spf13](http://spf13.com/) on the train while commuting to and from Manhattan.
* Coded in [Vim](http://vim.org) using [spf13-vim](http://vim.spf13.com/)
