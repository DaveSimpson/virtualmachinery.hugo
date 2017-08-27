---
author: Dave Simpson
date: 2015-02-11 00:29:00+00:00
draft: false
title: VMware launches vSphere 6.0 and various other happenings
type: post
url: /2015/02/11/vmware-launches-vsphere-6-0-and-various-other-happenings/
categories:
- Posts
thumbnail: "img/20150211vsphere60.png"
description: "vSphere 6.0 Launched"
tags: [VMware,vSphere]
---

The worst kept secret in Hypervisor history was finally revealed last week, when VMware went public with the launch of vSphere 6.0 (alongside a swathe of other products) in what they are calling their biggest ever release. So big in fact that it's taking 28 days to get through it if you read up at [onecloud.vmware.com](https://onecloud.vmware.com/?src=vmw_so_vex_dsimp_889), a microsite introduced under the title "One Cloud, Any Application". 28 days is handy in that it gives people time to digest a range of features and also write additional contributions (more on that later).  
  
The first week focussed vSphere itself, now followed by VSAN as week 2 and clearly there is more to come. The site is being updated every day with new content, there's a lot of VMware sourced technical information to be found there as you would expect, plus links to blog posts written by the community, which were solicited from vExperts in advance of the launch announcement. The idea here being that VMware themselves would drive traffic to bloggers sites by linking their posts right from the onecloud site itself. Nice idea. As the February 2nd launch took place in the US, bloggers posts were dropping as new content was published on their sites and since the VMware launch itself seemed to take an age to start up, we had the situation where blog posts were announcing vSphere 6.0 before VMware did. The launch video can be re-watched from the oncloud site if folks missed the US launch or the other launches around the world - I wonder if it cuts off as suddenly as the launch event itself did? Great content and great features when the launch got rolling, lots of new advances that a lot of us have already got to play with, but then nothing! A bit disconcerting at the time, as I wondered if I was missing something else!  
  
Another site I want to point out is the [VMware vSphere Blog](http://blogs.vmware.com/vsphere/esxi?src=vmw_so_vex_dsimp_889), which contains some really useful updates on the new release and also a handy pre-notification of the changes that will be made to the [new hardening guide](http://blogs.vmware.com/vsphere/2015/02/vsphere-6-0-hardening-guide-overview-coming-changes.html?src=vmw_so_vex_dsimp_889) when it comes out. There's another post though that's caused more of a stir amongst the blogging community and that's entitled [Clarifying the Misinformation](http://blogs.vmware.com/vsphere/2015/02/vsphere-6-clarifying-misinformation.html?src=vmw_so_vex_dsimp_889) which refers to changes which were made since the latest release of the beta and the release code. Unfortunately, all the efforts VMware put in to getting the community to write blogs explaining all the new features were of course based on the beta code, there was no time for any changes to content to be made as there was no word from VMware beforehand to tell bloggers what had changed. Misinformation seems a bit harsh, a bit finger pointy, I mentioned the hardening guide post earlier partly because it's a useful post about a useful thing, but also because it is a notification of changes that will be made. Should have done the same thing with the bloggers ideally, give them a chance to shine VMware, you took the gloss off this a bit and I can see why a number of well known folks in the community were a little upset by this!   
  
Still, There is a heck of a lot of good content out there and a heck of a lot of new features coming "sometime in Q1". Some of the highlights in no particular order;  


  * Up to x4 increases in configuration maximums (everything as good or better than Hyper-v 2012 R2)
  * Instant Clone of VMs (project Fargo / VM fork)
  * OpenStack on vSphere (VIO)
  * Linux Container support
  * FT support increased to 4 vCPU VMs
  * Increased capability on VCenter Appliance
  * Long Distance vMotion (100 ms RTT)
  * vMotion across switches (be they standard or distributed) - across L3 boundaries
  * Content Library for template / ISO / OVF files - 1 central location and shared subscribers
  * A faster web client (yay!)
  * VVOLs - virtual disks written natively to arrays, no more LUN mappings
  * VSAN 6.0 - Tier 1 workload ready
  * VDP included in Enterprise Plus - well, VADP actually, for free. 
  * VMware Certificate Authority - an optional service to ease the pain of certificate management 
  
A lot there, each worthy of a blog post in it's own right. I think I will wait for the code to drop and then pick a couple of favourites!  
  
  

