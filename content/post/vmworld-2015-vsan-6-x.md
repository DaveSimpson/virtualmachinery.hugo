---
author: Dave Simpson
date: 2015-09-01 13:37:00+00:00
draft: false
title: VSAN 6.1 and 6.NEXT
type: post
categories:
- Posts
- VMworld
thumbnail: "img/20151013vmworld2015train.jpg"
description: "VMworld US 2015 VSAN stuff"
tags: [VMware,VMworld,VSAN]
---

Cormac Hogan has posted a couple of blog posts in the last 24 hours detailing the new features offered by the newly announced (today?) release of VSAN 6.1 and also lifted the veil somewhat on what can be expected in the next release, including another VSAN beta signup offer.  
  
Whatever you may think about the adoption rates for VSAN there's no arguing with the pace of development coming out of VMware for this technology. Obviously, VMware had a lot of ground to make up from the initial 1.0 release, but they never shied away from that fact. These two posts are evidence of the rapid development rate for VSAN.  

In a Nutshell, 6.1 sees support for SMP-FT fault tolerance, so good to see VMware tech supporting VMware tech, plus support for Stretched clusters (both L2 and L3) along with guidance on what to use when if you are looking for a highly available solution across 2 sites. Something I welcome as a throwback to the LeftHand Networks days is 2 node support for Remote/Branch office installations, where the quorum/witness role is fulfilled by a specific VM appliance. There's also Healthcheck v2 and support for new types of flash.  
  
The proposed feature set for .NEXT includes the long awaited Deduplication, although so far no mention of if this is pre-write, overnight or with an option to run whilst destaging from flash to spinning disk (if you are not using an all flash VSAN). The other features mentioned are Erasure Coding, which will allow VSAN to offer RAID 5 and 6 in addition to RAID 0 and 1, which will increase the amount of usable capacity offered by VSAN storage arrays and end-to-end checksums - meaning not just local to the device, but across the piece, which looks like it will protect data from issues on the network or from hardware/firmware problems.  
  
If Compression is on this feature list at some point then that would round off the features which most folks could list to rule VSAN out of consideration. An interesting comment from Cormac on his blog in that he is only allowed to talk about the features in .NEXT that he's listed, so to get more answers on that, [sign up for the beta](http://www.vmware.com/go/vsan6beta?src=vmw_so_vex_dsimp_889).  
  
#### The original posts are found here:  
  
[The 6.1 Features post](http://cormachogan.com/2015/08/31/a-brief-overview-of-new-virtual-san-6-1-features-and-functionality/#more-5489)  
  
[And Cormac's 6.NEXT announcement](http://cormachogan.com/2015/08/31/vsan-6-next-beta-a-glimpse-of-the-future/#more-5496)  
  
  
  

