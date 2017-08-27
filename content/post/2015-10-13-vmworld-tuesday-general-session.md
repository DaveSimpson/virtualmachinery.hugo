---
author: Dave Simpson
date: 2015-10-13 11:48:00+00:00
draft: false
title: VMworld Europe 2015 Tuesday General Session
type: post
url: /2015/10/13/vmworld-tuesday-general-session/
categories:
- Posts
- VMworld
thumbnail: "img/20151013vmworld2015banner.png"
description: "VMworld Europe 2015 General session, live from the Blogger Table"
tags: [VMware,VMworld,Community]
---

## Setup
A better start than last year since we were able to set up in the Hang Space before anyone started speaking. I managed to get a seat along with [@julian_wood](https://twitter.com/julian_wood), [@scott_lowe](https://twitter.com/scott_lowe) and [@vcdxnz001](https://twitter.com/vcdxnz001) and had a go at the minimal setup, iPad for blogging, iPhone for twitter and a bluetooth keyboard. That wasn't as "corridor warrior" as I had hoped, it doesn't really cut it as a practical solution, is's simply too slow to keep up and I struggled to blog and watch the twitter feed at the same time.  

## Intro
Jean-Pierre Roulard opened up proceedings for us, similar to the US event, the first thing on the agenda is destination giveback and also vmwomen, so again, community before product, which is nice. Then the handover to Carl Eschenbach, Within a couple of minutes of coming on, he mentions the big one, the Dell/EMC merger. VMware will continue as it is he says. Then a Michael Dell video, He apologises for not making it to Barcelona, stating that it has been a busy couple of days. I guess it took a bit longer that that, but we get the point.  

  
The one cloud, any application, any device (any time) message comes back again, this time with additional commentary about the fact that one cloud is not actually a single location cloud, it should be a single cloud platform, spanning on premises and off-prem also, utilising a Cloud Management Platform.  

## Telco's  
Now some new announcements, VMware vCloud NFV (Network Function Virtualisation) for the Telecoms industry, coupled with VMware Ready and Carrier-Grade support to ease the move to NFV. NFV is tagged as "One Cloud for the Telecom Network" it is placed between the "one cloud" mentioned earlier and the telecomservices such as VoLTE and VEPC (which apparrently are Virtual Elastic Mobile Services). You can see this below;  

[![NFV](/img/20151013nfv.jpg)](/img/20151013nfv.jpg)

Novamedia and Telefonica on stage, but it was impossible to hear a lot of what the guys were saying, unfortunately. However, what I did glean was that Novamedia rolled out four SDDC datacenters in a year utilising EMC and NSX to build their stack.  

## Cloud Native Apps 
The faces on stage are rotating quickly, Ray O'Farrell comes on to introduce Kit Colbert, who is getting in to the vmwcna space. vSphere Integrated Containers are outlined by Ray and Kit, with the discussion on moving from a large VM with a lot of containers within it towards smaller VMs running directly on vSphere virtual container hosts. I can see how this can work, VMware have an optimised linux kernel, which schedules workloads really well, so pull out all the things that containers do not need (vMotion, HA) and leave in the aspects they do to make a really thin jeVM (just enough VM) platform to manage storage connectivity, security, scheduling and all the things that containers alone just cannot manage.  

[![jeVM](/img/20151013jevm.jpg)](/img/20151013jevm.jpg)

## Cloud Localisation  
Bill Fathers also up on stage, "now for the cool stuff". He's addressing data sovereignty which is a really important topic for the majority of corporations with a global reach. So many constraints on where that data can be domiciled and I am not sure that any cloud solution is 100% able to simply manage that. We are going to need those localised cloud solutions that the vExperts were tweeting about and discussing whilst this was going on. Then Bill goes on to cover the unified hybrid platform in place between your on premises cloud and the public cloud, and vMotion between those two locations again, which is really cool, but again, needing data properly domiciled. Bill finishes with the point that 'latency kills revenue' so localisation is clearly going to have to be a thing.  

## SDDC  
And on to Raghu once more, which is similar to the US presentation, with Yangbin Li and the EVO SDDC Manager.  Also VMware Validated Designs, the two are shown side by side, the intention being that if you want to go all in, then EVO SDDC will provide you the whole thing in one integrated bundle, if you wish to utiiise your own hardware, then a VMware Validated Design will be there to cover you, since it matures and updates as new products are relaesed, enabling customers to remain on a validated solution through time. Yangbin also gets to officially announce vRA 7, which was showing up on the internet earlier today.  

[![VMware Validated Designs](/img/20151013bloggers_v2d.jpg)](/img/20151013bloggers_v2d.jpg)

_lots of interest in V2D from the bloggers area_

Cross Cloud vMotion is demonstrated again, getting workloads in and out of cloud has been a huge sticking point for so many people, that this is going to be a big thing. Coupled with VMware's unified hybrid cloud management approach, then you are able to reach in to vCloud Air, AWS, OpenStack, this is really getting some reach now.  
