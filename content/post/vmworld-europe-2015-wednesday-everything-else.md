---
author: Dave Simpson
date: 2015-10-18 14:09:00+00:00
draft: false
title: VMworld Europe 2015 Wednesday everything else
type: post
categories:
- Posts
- VMworld
thumbnail: "img/20151013vmworld2015train.jpg"
description: "VMworld Europe 2015 "
tags: [VMware,VMworld,Community,VMUG]
---

## Rubrik
The first thing I had on my agenda after the General Session was to take a look at Rubrik, one of the companies that have been getting a fair aount of buzz lately and so I took the opportunity to go and find out why. A hyperconverged type solution, a number of blocks (briks, obviously) a nice interface, dedupe, replication, all that seems to be the thing to do these days. What was noteworthy was the calibre (and diverse origins) of the people who started the company and the functionality around search within the backups.  

If you know how to use Google, then you know how to use it they say and that is cleary so, search for a part name of a VM and you are returned the results, search on in to files and you will get results. You can go right in and download or restore individual files from a range of backup instances, clever stuff. Looks to me like the initial intention was to avoid backup tapes alltogether, but then the requirement for some companies to still have to be able to resort to backup media if required has caused that to be an option here as well.

## TAM Session - vROps Roadmap
I then made it to a TAM session about the vROps Roadmap (vROps being part of the VMware Cloud Management Platform layer) before another important mission was also accomplished today. Collecting the SolidFire vExpert promo Cards Against Humanity deck. That should provide some fun times in future, IT Geeks, Beer, Comedy card game, sounds good to me.  
  
## An Actual Normal Session
I was pleased that I took in Mike Foley's engaging security session INF5177 vSphere Security - Fact vs Fiction. This session laid out what people think is the most problematic aspect of virtualisation from a security perspective (VM escape), explained why that is so unlikely to happen, (_really_ high cost, small number of people who know enough about how to do it) and went on to explain the sorts of things that really should be of more concern to security and audit teams (physical access, patching, the overprovisioning of rights and roles, social engineering, in fact all the same things that impact any IT system). I didn't catch many breakout sessions as I can get them on recording later, but this one was good.  
  
There was a VM escape demonstrated once, at Black Hat back in 2007, using an unpatched Windows XP VM running in an unpatched VMware workstation release with old VMware tools. If there's been something since, you'd imagine that it'd be all over social media nowadays. The key lesson here is patch your stuff, folks release security patches for a reason, here VMware is no different to anyone else. Of course, there have been a number of examples of VMware patches causing issues themselves, so you still need to do your testing and evaluation. If you break out of ring 3 on a VM, you are running in ring 0, on that VM. You then still have to get to ring 3 of the hypervisor that this is running on and then in to ring 0 of that hypervisor as well, which is why this is hard to do - the hypervisor provides additional levels of isolation hat have to be worked through.  
  
Knowing what to do about this in a VMware perspective is good information to have to hand though. You should make your security guys watch this session if you have access to the recording of it :-)  

## Hall Crawl  
The Solutions Exchange becomes the centre of attention for a lot of people in Wednesday evening, because vendors stands also have beer and food on them to tempt you to get in there for a chat whilst you are waiting for the VMworld party to start. This is the noisiest that the Solutions Exchange gets, which is no surprise.  

## Customer Appreciation Party  
This year, the band was Faithless, who I'd never seen live up to this point, so I had a good time. As I'd predicted earlier in the week, some of the folks who were more rock centric than fans of the electronic genre enjoyed the show, as I knew that Faithless do play proper instruments live.  

[![Faithless](/img/20151018faithless1.jpg)](/img/20151018faithless1.jpg)

[![Faithless](/img/20151018faithless2.jpg)](/img/20151018faithless2.jpg)
 
Wednesday night is an early night usually for me, which is relative I guess, it was the only time I was 'home' by midnight.
