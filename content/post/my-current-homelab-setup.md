---
author: Dave Simpson
date: 2016-11-02 09:00:00+00:00
draft: false
title: My Current Homelab Setup
type: post
categories:
- Posts
- Homelab
- vDM30in30
thumbnail: "img/20161102nucgen5.png"
description: "Discussing my current Homelab setup."
tags: [vExpert,homelab,vDM30in30]
---

As a confirmed Homelab freak and a#vDM30in30 participant, I guess that a post on the content of my lab would be pretty much expected. I'm a permanent member of staff in a large company, so I do have access to a considerable amount of kit on different continents within which I can play around at times, but I'm still of the opinion that having something to mess around with at home is viable. That said, I'm also a fan of [what Ravello got up to ](http://www.virtualmachinery.co.uk/2015/08/time-for-cloud-lab.html)in the cloud a while back, so it may come to pass that I don't have another homelab quite like this one again..  

  
Inside the house you'll find the usual broadband router, wifi type setup, with a Synology DS413J NAS at its core, serving up the tunes for the Sonos, the media for the TV and the like. Out here in the man cave, I'm at the other end of the garden, past the barbed wire, the spotlights, cameras and the horde of highly trained attack dogs.  
  
In here I've got my own wi-fi router, so that handles my physical segment (this PC, work laptop, printers etc) and then hooks into the almost ubiquitous homelab staple, the Cisco SG-300. I did have an old Catalyst 3550, but it was twice the size and made me think I was still in the datacentre, rather than somewhere supposedly comfortable for working. The SG-300's totally silent, which is a godsend. This setup allows me to run all the VLANs you'd want to have a lab running, management, storage, vMotion, VMs, you name it and none of it has to get stuck in an unmanageable Virgin media excuse for a router.  
  
The lab runs on a small stack of[ D54250WYK NUCs](http://www.virtualmachinery.co.uk/2015/03/vexpert-homelab-5-esxi-60-nuc-nuc-nuc.html) now backed by a Synology DS216+II. I used to have an Iomega ix-2 doing this job, but the increasing number of horror stories I had heard about the loss of one drive wiping the other meant that I felt a small trade-up was worthwhile, plus Docker runs on the new one :-) So overall, not the biggest compute cluster in the world, but good enough for most things that I need to fiddle around with.  
  
I work from home a couple of days a week now, so this setup has to be pretty solid and so far, it's going really well. However, Winter is Coming (even for tropical Brighton) so I do have to be somewhat prepared. The heater in here is plugged into a WeMo plug, so if I am working from home, I can have the heater come on according to my normal scheduled routine, or if there is something ad-hoc going on, then I can basically "email my heater" [courtesy of IFTTT](https://ifttt.com/recipes/132322-use-siri-to-toggle-wemo-switch-via-email-siri-wemo) and turn the heater on from my bed (2 seperate wi-fi networks, remember, so an emails faster than making sure I'm on the right wifi).  
  
The highlight of the lab setup though is probably the thing you'd not think of, but you should. No, not my monitor, although I do love my widescreen LG, I mean my chair. I used to have one of those fake leather executive chairs that you find in all the office supply catalogues. You know the ones, nice 5-wheel base, but not much else, not adjustable, no support, nothing. One night I attempted to get out of that and ouch, back pain, much swearing and after some agonised hobbling upstairs to bed, I swore that was it.  Enter the [DX Racer Drifting Series ](http://www.dxracer-europe.com/drifting-series-1)chair that I'm sitting in now. Fully adjustable, it pretty much goes flat (not that I fancy trying to have a kip in it) and comes with all that lovely lumbar support, additional side support, cushion for your neck and so on. I'd done my back in once before, and to be honest, the only place where I got any comfort at all during 3 or 4 miserable days was behind the wheel of my car. Not at work, not in bed, not on my sofa. This chair is like a car seat. That's the Racer in DX Racer for you, they were a racing seat company, now they make chairs for esports pro's, [Twitch streamers](http://twitch.tv/) and the like, as well as folks like me who just want a bit of comfort. You owe it to yourself to sit in a decent chair, future you will thank you for it.
