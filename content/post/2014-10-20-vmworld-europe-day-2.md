---
author: Dave Simpson
date: 2014-10-20 17:34:00+00:00
draft: false
title: VMworld Europe 2014 - Day 2
type: post
url: /2014/10/20/vmworld-europe-day-2/
categories:
- Posts
- VMworld
thumbnail: "img/20140825vmworld.jpg"
description: "VMworld Europe 2014 Day 2"
tags: [VMware,VMworld,Community]
---

I'm on a bit of a roll now! The 'second' day of VMworld Europe started with another keynote, just the same as San Fran (same general format, same general content). Fortunately for those of us wanting to blog/tweet during this, the doors that were closed yesterday were open by the time I got to the hangspace, so I was in and settled with a coffee and pain au chocolat before 9am. This time I chose "Recharge Island" instead of the bloggers table, mainly cos I didn't have a blogger badge or pass and there was less stuff between me and the big screen this time.  


## Keynote  
Once more, this is the session in which some more of the technical content is revealed when compared to the previous day, but again we have heard a lot of it before.   
  
Carl Eschenback had the lead in this session and introduced a number of videos followed up by chats on stage. Included in this section were some interesting points - for instance, SAP are using 75,000 VMs and are refreshing those at a rate of 30,000 a month to meet changing use cases. Those numbers make my head hurt. Then Tom Stockwell of Vodafone challenged us to consider if our business success is driven by apps/services or infrastructure. One of the themes this year was the move towards considering that hardware virtualisation is a done deal, we now need to focus on rapid app deployment. This was already mentioned in the TAM day introduction and was picked up again here.  
  
Another recurring theme is Policy Based Management. It seems that's my personal 3-word catchphrase right now and it was echoed again here, within a cloud management framework based upon the pillars of Security, Governance, Application Availability and Service Costing & Metering.  
  
One of the interesting developments slated for vSphere 6.0 is the long distance vMotion and cross vCenter vMotion functionality. I don't need to go in to great detail here cos Julian Wood has already done it (in August) over at [WoodITWork](http://www.wooditwork.com/2014/08/26/whats-new-vsphere-6-0-vmotion/). I've seen the fiddly tediousness about having to migrate VMs from a VDS to a VSS to be able to move to another vCenter with a VSS before putting them back into a VDS again, can't wait to see the back of that particular game. This session also showed us some demonstrations, the integration of openstack right in to the vSphere client is well done and there was also a look at the vRealize Automation mentioned yesterday. There was also mention of the vRealize Managment Suite 6.0, which was announced at VMworld Europe on Monday - vCOps / Log Insight etc. rebadged. More on that [here](http://blogs.vmware.com/management/tag/vrealize-operations-manager).  
  
Then there was the section on NSX. I definitely like the idea that we are now able to use microsegmentation to apply network policy to individual VMs and what's more, when you delete a VM, any specific rules that were put in place for it get deleted as well. Nice tidy firewall configs are something lots of people aspire to!  
  
Again, I had an 11AM session I needed to get to so I was out of the keynote before it finished for the second day running.   
  
## Session: BCO2701: HA Best Practice / FT Tech Preview  
GS Khalsa was doing this one so I was pretty sure it was going to be decent! I wasn't disappointed. We started off with an overview of the basic best practices for HA, such as network settings and heartbeat datastores, then went through the differences with VSAN (as in you cannot use VSAN as a heartbeat datastore) and on to considerations for host isolation response in different situations. You can find a great summary of this at the [VMware blog](http://blogs.vmware.com/vsphere/2014/05/vmware-virtual-san-vsphere-ha-recommendations.html) site. Then we also had a run through admission control before moving on to the second half of this session, the FT Tech Preview.   
  
It's now common knowledge that FT will cover up to 4 vCPU VMs, as this has now been announced in both VMworld day 2 keynotes this year. FT has been compeltely re-written to do this and is now basically a perpetual vmotion and storage vmotion with many checkpoints per second. There's a list of constraints still within the new SMP FT, such as needing a 10 gig network and no VSAN/VVOL support yet, but also some loosening of the previous limitations, so you can now have paravirtualised drivers, any disk type and only the FT config file and a 'tiebreak' file need to be on shared storage. That's quite neat. Protecting a vCenter is now a consideration for and FT use case, but you cannot use VSAN remember, which has also been a VMware suggested use case for storage in a Management Cluster. Handy if you can keep vCenter down to 4 vCPU. The secondary VM doesn't use any CPU whilst it is the secondary, but there is still a limit of 4 FT VMs or 8 FT vCPUs per host as default (primary and secondary count for this) and also a limit of 64GB memory.   
  
GS also went through VRAS - the vSphere Resource and Availability Service. This is a webpage which allows you to load up a dump file and it will tell you how many VMs will be impacted and how many not impacted if you lose a host (or more than one host) from a cluster. This will work with any vSphere 5.x platform and will be out in a few weeks - watch out for this, it's really cool!  
  
## TAM Customer Central
After this I decided that I would try to rip up my carefully compiled schedule as I had received an early morning email from the VMware TAM folks telling me that I could turn up at the TCC and try to book in to some more of  the TAM sessions I had previously been told were full. Interesting!  
Anyroad, I managed to grab another two TAM sessions, the first on the roadmap for SDDC and the vCloud Suite and the second on the roadmap for vCAC (yep, no-one has got used to the new name yet!). These sessions were really good, but really NDA. I'm not used to getting this type of content thrown at me, so it was great to be able to go over stuff, ask questions and hear the questions being asked by others, especially in cases where I was less than familiar with the content being discussed. Then I still had time for a final breakout session of the day.  

## Session: STO 1965: VVOLs Technical Deep Dive.  
Well, this was not as much of a tech deep dive as I had hoped, when compared to the introductory VVOLs session I had attended earlier in the week. Slightly disappointing, I could have ducked this one and still had a good idea of what VVOLs will bring to the table. Or ducked the first one, as this session started with a recap. This session had another vendor up on stage as well, Vaughan Stewart of Pure Storage this time. Again, interesting to see a vendor right up on VVOLs from the get go, as were 3PAR, but I've never used either of those vendors. Still, this was my only scheduling issue, so not so bad.  

## Solutions Exchange
I also managed to revisit the solutions exchange today, both before and during the "Hall Crawl", more swag was bagged and more information sheets were collected. I'm not going to say too much about the solutions exchange, since I cannot say too much to the people _in_ the solutions exchange, which is an interesting position to be in!  

## Hall Crawl and Customer Appreciation Party  
The Hall Crawl features booze, since it's the warm-up to the VMworld Party, which is thrown in the general session space, so at least I did get to go under the "General Session" banner, since I had avoided going there to see either of the keynotes that take place therein. I'd hooked up with the Xtravirt crew by this point, who I know from the #LonVMUG events, so they knew the form. There was food, there was beer, there was Simple Minds. A pretty safe choice I'd say, given the general age of the folks at a VMworld.  Even the yougsters knew some of the songs and there was enough applause for an encore, rock and roll!  
