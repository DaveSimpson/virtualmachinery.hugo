---
author: Dave Simpson
date: 2016-11-06 10:00:00+00:00
draft: false
title: 'Site Outage - #vDM30in30'
type: post
categories: 
- Posts
- vDM30in30
description: "A DNS outage on my blog got me thinking..."
thumbnail: "img/20161106onejob.jpg"
tags: [DNS,vDM30in30]
---
I've just had to recover virtualmachinery.co.uk from an outage. Fortunately, this was my first experience of my blog being unavailable since I added the custom domain on to the front of it a couple of years ago, but non the less, it's left a sour taste in my mouth. Repairing it has also bitten into my blogging time somewhat, but has also given me fuel for a blog post.  
  
I'm right in the middle of blogging for the #vDM30in30 challenge, so I am giving my site a lot more attention than normal so I spotted the problem and set out to investigate.  

What had happened was that my domain registrar had decided to wipe my DNS settings, so visitors to the site were presented with this;  


[![1and1 default website](/img/201611061and1.png)] (/img/201611061and1.png)
    
Yeah, sorry 1and1, don't like to point the finger or anything, but it's you. I did click on the “Why is this page displayed” link, but unfortunately, it didn’t say “because we’vemade a change that screwed you over, Dave. Please accept our apologies”. Instead it contained some junk about being helpful and putting this page there so visitors don’t get an error message. I much preferred it when my own content was there instead, as I'd left it. Fortunately, the content is elsewhere, so that was all safe.  
  


[Andy Nash](https://twitter.com/andynash99) dropped me a tweet about the problem too. Cheers mate!  
  
Now I don't mind where there's an issue and someone accepts responsibility, because things do go wrong, mistakes get made. I've certainly cocked enough things up over the years. but when I do, I'm the first person to put my hand up and say so, ideally before anyone else finds out. Being asked "What have you done?" as the first question never goes down well when you're calling about a problem. Clearly, it wasn't me who decided to wipe my settings and point them back to the generic ISP holding page, cos I don't even know where that is! After I assured the person that I was talking to that I had not trashed my setup, it was revealed that I was not the only one impacted, as they offered to add my call to the ticket for other people who have the same problem at the moment. So there is a problem, after all! I see! At least I wasn't blamed for causing the problem for anyone else :-)  
  
Unfortunately, the internet being what it is, it turned out to be impossible to revert my settings, so I had to do it myself when I was able to get back in front of my PC. In the meantime, I had been offered a refund on my latest bill, which is a nice gesture and not something that other companies have done when I've had problems with the services that they provide. Unfortunately, domains are so cheap that the slightest problem costs more to fix than you're likely to get back. Still, I appreciated the offer, which was unexpected to be honest.  
  
Hopefully by the time that this post drops, everything will have settled settled down again. On the bright side though, like everything else, this was an opportunity to learn.  
  
I've picked up a decent online dig tool, over at [kloth.net](http://www.kloth.net/services/dig.php) which I used to verify that I could see my settings changing out on the web as I replaced CNAME settings and so on.  
  

[![dig at kloth.net](/img/20161106dig.png?w=300)] (/img/201611061and1.png)

Can you dig it? (Oh yeah)
  
  
I now know the difference between an http redirect (viewer sees the url change to the target site and sees the content from the target site) and a frame redirect (viewer sees your url but the content comes from the redirected site). One of  those things that I knew happened, but not what they were called, now I know.  
  
This blog is currently running from Blogger, cos it's really easy to use, so 1and1 only have to do the DNS bits for me. If anyone has any suggestions for companies in the UK that don't revert your DNS settings to defaults, please let me know! Should I move off Blogger one day? I don't know. Seems like a lot of work for little reward, as I've got no issues with them. Again, if you reckon I should move as you can't believe I'm not taking advantage of some amazing feature, then I am all ears...  
  
  

