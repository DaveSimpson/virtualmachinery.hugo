---
author: Dave Simpson
date: 2015-08-31 19:28:00+00:00
draft: false
title: VMworld US 2015 Keynote thoughts
type: post
url: /2015/08/31/vmworld-2015-keynote-thoughts/
categories:
- Posts
- VMworld
thumbnail: "img/20151013vmworld2015train.jpg"
description: "VMworld US 2015 General Session"
tags: [VMware,VMworld]
---

So here we go, The Keynote from the first day of VMworld 2015, San Fran. This is more a stream of thought than anything totally structured/sensible and is partly my notes to see what I need to go look at later on!  
  
Apps and Cloud huh? Opening with a video before [Carl Eschenbach](https://twitter.com/carl_eschenbach) takes the stage. There are a record 23,000 folks attending in person this year, somewhat different from the 1,200 in the first year, plus loads of folks like me watching from further afield.  
  
Nice to see that the VMware Foundation and #vGiveBack are mentioned by Carl before anything else.  

  
Some key messages and buzzwords;  
"Run, Build, Deliver and Secure any app at any time, any place" Oh, on any device!  
The VMware Commitment of Freedom Flexibility and Choice.  
If you've seen any VMware presentations in the past year or 2 you will have heard this kinda thing before.  
  
Application delivery models are changing to cover Cloud Native Applications as well as what are already being called legacy Applications. I think it's a bit early to call all that traditional stuff legacy, but there you go.  
  
Carl goes on to talk about One Cloud, but it soon becomes clear that this One Cloud is actually a unified Hybrid Cloud, spanning on PremiseS and off PremiseS, This is part of the One Cloud, Any Application, Any Device model that VMware have been talking up for a while now.  
  
Mike Benson, DirecTV CEO on stage discussing streaming of crap boxing matches and over 20 years of the NFL.They're using NSX to help them deliver additional content around the product, such as fantasy football and stats overload.  
  
Here comes Bill Fathers, he knows how to talk properly. SRM as a service in the cloud sounds really handy. This wasn't properly named as far as I saw, but this is what they are calling VMware SRM Air. This is SaaS based DR with failover and failback, into and out of the cloud. Like most clouds, the fear of not getting your stuff back does sway people away from adoption, so the failback portion here looks interesting. Something to add to my VMworld Europe watchlist.  
  
Now we all know that latency kills apps, the trick that Bill is talking about in his content is the ability to treat local datacenter and cloud based services as a single resource and also using the same security policies. Micro Rental of Pets? Really? Is that a thing? Totally distracted there.  
  
[Raghu Raghuram](https://twitter.com/raghuraghuram) comes on stage as well. The Unified Hybrid Cloud is the thing.  
Simplify the private cloud to make it easier to run on local infrastructure by turning infrastructure in to software.  
Extend the application components out of the corporate datacentre in to the service provider datacentre.  
Reach vCloud Air for your SRM, Application overspill, Dev and other such requirements.  
  
And now [Yanbing Li](https://twitter.com/ybhighheels) as well, to look at engineering innovations. The Evo SDDC Manager is the first new product announcement being discussed properly. This couples the vRealize Suite, NSX, VSAN and vSphere within a 2 hour build time for a solution, which is based upon EVO:Rack. It also covers the management of your ToR switches, to boot. As long as you want the entire VMware stack, you are good to go. No mention of if it is practical to add other storage solutions to this as well, even if only for backups (as per the newly announced VMware Validated Designs) or the content library or so on. VMware do mention that you can buy SDDC now like you can servers, without worrying about vendor lockin, but this just runs VMware, so you may be locked in, you just have to decide if that matters to you,  
  
Oooh! Cross Cloud vMotion. Interesting. I guess that makes sense though, since we had cross vCenter vMotion and Long Distance vMotion announced in vSphere 6.0.  vMotion in to vCloud Air is pretty good, you've just got to have the correct tech at both ends, so I can't see this becoming ubiquitous any time soon. Oh, wait! Ravello Systems lets you do this already, from AWS to Google and back, as long as you're running their nested virtualisation (I got other posts on that good stuff already).  
  
Next was Virtustream, but I had to go get my dinner else angry wife, so I missed that part. I will be interested to see the direction they take though as the new part of the Federation. I did get back in time to see [Rod Rogers](https://twitter.com/rjrogers87) say we need to keep our eyes peeled for some announcements coming soon!  
  
Next up the newly appointed CTO, [Ray O'Farrell](https://twitter.com/ray_ofarrell), talking @cloudnativeapps - I was just wondering where [Kit Colbert](https://twitter.com/kitcolbert) was and here he comes. Now we are talking containers. More correctly, vSphere Integrated Containers and the Photon Platform. The word Microvisor was coined, seemingly this is a thinner hypervisor, without the "bloat" of features that are not required for containers (like vMotion) but featuring sufficient management through a single pane of glass to offer isolated VMs that can be spun up really quickly. jeVM - Just Enough VM - a 25mb footprint with no initial memory footprint, spun up in under a second. That's the Photon Machine bit.  
  
So, 2 strands here then, full fat vCenter with the original Photon and Bonneville aspects for your hybrid of "legacy" and "cloud native" stacks in VIC and the newer Photon Controller and Photon Machine if you want to be running and managing just containers. There's a lot more to look in to about this (and probably plenty of time to do it in, but let's not be complacent).  
  
  

