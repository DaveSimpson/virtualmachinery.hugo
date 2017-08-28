---
author: Dave Simpson
date: 2014-08-25 23:21:00+00:00
draft: false
title: VMware enters the Hyper-Converged space with VMware EVO.
type: post
categories:
- Posts
- VMworld
thumbnail: "img/20140825evorail.jpg"
description: "Project Marvin - EVO:Rail and EVO:Rack "
tags: [VMware,VMworld,Evo]
---

In a move that justifies (if that's the right word) the developments made by Nutanix, Simplivity et al, VMware announced two releases of their Hyper-Converged Infrastructure Appliance (HCIA) products, which are called VMware EVO. This is the Project Marvin initiative which has been whispered about for a while since an internal VMware poster was seen up on a wall by someone who shouldn't have seen it! The EVO part means Evolution and the product names RAIL and RACK are down to the amount of space they take up in the datacentre. Rail for the fact it goes in on one set of rails and rack, well, it's in a rack.  
  
EVO:RAIL is a 2U/4Node unit, with each node running vSphere and VSAN and functioning overall as a vSphere Cluster. There is a specification available to partners, who have to build hardware to support at least this standard. These partners include Dell, SuperMicro, EMC and Fujitsu, who most people will know, plus Inspur from China and NetOne from Japan. interestingly, no HP on this list, which is what has raised most eyebrows to this point. Definitely a smart move to leave the hardware to the hardware guys, but since VMware EMEA CTO Joe Baguley has said that if something needs specific hardware then you cannot call it "software defined" then is this really a building block of the Software Defined DataCentre? Well, maybe this is actually Software Defined Hardware (SDH)? Hahaha, you heard it here first.  
  
The configuration of EVO:RAIL appears extremely simple. It's also an HTML5 interface, so you can administer it from pretty much anything. Setup only takes 15 minutes, which is impressive. This gives you a fully prepared VCenter, 4 hosts in a cluster and standard switches, with your VLANs etc. in place. Additionally, you can add up to 3 more units to the first one, with them being detected by VMware Loudmouth (think Apples bonjour service) so expanding your setup is easy too. So far so good.  
  
Who better to go over the details of this than [Duncan Epping](http://blogs.vmware.com/tribalknowledge/2014/08/vmworld-2014-vmware-evorail-building-block-software-defined-data-center.html), VMware's Chief Technologist.  
  
  
EVO:RACK is a much bigger beast, with full vCloud Suite and NSX built in, again, with its own management built in too. EVO:RACK can also scale up to tens of racks it seems, so that is pretty much your entire datacentre covered. Clearly targeted at more enterprise level operations, IaaS and VDI use cases are to be addressed first, with more to follow, such as PaaS and big data. The deployment model here is to have a rack implemented in under 2 hours from being pushed into the data hall to running workloads. Rack-n-Roll they say. Geddit?  
  
See what Raj Yavatkar has to say on this, on the [VMware Office of the CTO blog](http://cto.vmware.com/evo-rack-tech-preview-vmworld-2014/).  
  
  
So, I briefly mentioned 2 established vendors in this space at the start, briefly by design. I don't think they'll be overly worried at this point, especially not when you look in to this and see that they're some way ahead, feature wise. For instance, there's no dedupe in VSAN at this point and that is a key factor for someone like me at the moment. Simplivity is built on the fact that data is never written to the storage twice (well, other than the fact it's written to 2 different Simplivity devices at the same time) but then after that it's just metadata that gets written when duplicate blocks are sent to disk. That's likely to be pretty important if you are looking at spinning up a whole bunch of relatively identical workloads or are dealing with large databases etc. Then again, if you get EVO:RAIL then you get a 2u solution with 14TB of storage, that could well be enough!   
  
Of course, if you have a well established relationship with Dell or Fujitsa, for instance, with a RoBo office expansion to buy for, then EVO:RAIL really fits the bill. Especially given the speed and simplicity of the setup, no more weeks on the road visiting many branches of your company - but do you need another vCenter each time you need a few hundred VMs?  
  
I'm interested to see how this goes for the hardware partners (and if we see more partners) and also how it may push progress on VSAN in particular. I am not sure that it's the right fit for me personally within my company right now, but I can see the use cases being mentioned getting sales, for sure.
