---
author: Dave Simpson
date: 2017-08-27 16:13:00+00:00
draft: false
title: 'Discuss Disqus'
description: ""
categories:
- Posts
tags: [blog]
thumbnail: "img/20170827disqus.png"
---
For website comment integration, Hugo supports [Disqus](https://disqus.com/) out of the box. For this to work, you will need to be set up as a Disqus user and  then [create a Disqus site](https://disqus.com/profile/signup/intent/). When this is done, you simply populate the disqusShortname entry in your config file. For me, the line

    disqusShortname = "virtualmachinery"

exists in my config.toml file.

Disqus guides you through all of the basic setup, it's very user friendly and I had no issues with that whatsoever. One word of warning though, you won't see the integration working properly on the local copy of your site, you have to have something out there on the internet to see things working. This happened for me as soon as I created a version of my site after my config file was updated. Disqus will appear as a comment function at the bottom of every post. This is a framework, so the frame sits within your static pages, the comments can be updated without you having to resort to running hugo to create anything. No point putting a picture in here, just look at the bottom of this page!

It seemed sensible to me to require some form of user signup to deter the anonymous spammers, but you have pretty much total control on the requirements for posts, simply let them through, have someone moderate them, have comments removed if they get downvoted sufficiently and so on. You're notified when you have moderation tasks to carry out, you can easily approve comments, mark them as spam or delete them, all from the Disqus Admin console. If you don't want to do that yourself, it's also possible to grant someone else moderator status so they can do this for you. Very thorough, I'd not used any of this before, but I had Disqus up and running within a few minutes.

So that was the situation dealt with for all new posts going forward. The reason I left this configuration off my day 1 task list (it made day 2) was that I wondered what I needed to do with my existing comments. Well, you've covered there as well. Disqus has a set of tools available on their site to import comments from Blogger or Wordpress or to amend the links to your blog if you change paths to a post, so comments can always follow your posts around.

Whilst I was waiting for my DNS changes to propagate around the internet (eww, Virgin Media, your DNS server TTL  is soooo loooong) it was time to set up the comments functionality. Now, I grabbed all of the existing comments from my Blogger site, but the format of my new static website had changed slightly, so none of the comments were mapped to the posts any more. This was easily remedied. First I went into the admin console and approved the posts, then I had Disqus mail me a mapping csv file which detailed every path to posts that had comments were mapped to. All you need to do is add the new path into the cell next to the old path, save, submit the file and wait for a script to process everything for you (says it can take up to 24 hours, but my short list of commented posts processed much faster).

I doubt that everything else will be this simple!