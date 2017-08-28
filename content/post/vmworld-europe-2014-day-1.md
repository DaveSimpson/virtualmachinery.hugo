---
author: Dave Simpson
date: 2014-10-19 20:49:00+00:00
draft: false
title: VMworld Europe 2014 - Day 1
type: post
categories:
- Posts
- VMworld
thumbnail: "img/20141019vmworld2014.jpg"
description: "VMworld Europe 2014 - Day 1"
tags: [VMware,VMworld,Community]
---

Admittedly, I'd already been in Barcelona for a while after the TAM day (partner day for most people) on Monday, so we'd already had confusion amongst the bloggers as to what day it was., perhaps we should stick with 'Tuesday' and have done with it? Apologies for any tense changes here, this post was mostly written at VMworld, but not published then.  

## Keynote  
This was my first opportunity to attend a European keynote, so I was hoping to be able to get ensconsed in the hangspace or the bloggers area and tweet or blog from there, whilst hoping it would be different from the US keynote. Unfortunately, the first 10 minutes were spent milling around outside the hang space with some of the better known UK bloggers, as we weren't allowed in! There were a number of big screens, plus coffee and breakfast nibbles going to waste, as we could see through the round window. Finally we got let in over 10 minutes late, so I missed almost everything that Maurizio Carli had to say,other than him introducing Pat Gelsinger. 

## Pat Gelsinger
Pat went through the same Fluid / Liquid routine from the US keynote, but there was a more Euro twist with features on Cancer Research UK and Lufthansa, plus commentary on how Ministry of Education Malaysia are connecting every student, 25,000 virtual desktops. That's impressive infrastructure.   

Pat then went over vCloud Suite 5.8 and vSphere 6, with the same script, so it was new in August and new again now, I suppose not everyone watches the US keynote, but it's somewhat odd hearing "new" followed by what we already know. Add vRealize Suite also, but then finally something that is new, [vRealize Code Stream](http://www.vmware.com/products/vrealize-code-stream), which focuses on the Continuous Integration, Agile, DevOps world. This is a beta, but from what was seen, it looks an interesting concept and it integrates with a considerable amount of other apps, vCAC, vCO (oops, v**R**O etc., sorry!) vCenter, Hyper-V, Puppet, Jenkins and so on. This is quite new to me, but the possibility to have software versions automatically rolled up through environments from the lowest to production automatically, once they meet certain criteria which have been predefined sounds pretty slick!

Then came the biggest announcement so far - the addition of HP and HDS as 2 new partners in the EVO:RAIL infrastructure. That's going to make life easier for a considerable number of people. The HP announcement was only secured in the last few days, it seems, but now there's 8 EVO:RAIL hardware partners with hardware to show off at VMworld. So an update to something previously announced, which was nice.
  
Then back to the known script, VMs vs containers. The Project Fargo announcement about the partnership between Docker, Google, Pivotal, VMware, in what VMware calls [containers without compromise](http://blogs.vmware.com/cto/vmware-docker-better-together/). 
  
The last bit I had from Pat was that NSX growth was up from 100 customers last quarter, when covered at VMworld US to 250 now, which is interesting for a new product that had not been relaesed through the normal distribution channels at this point. Also new today was the NSX partnership with Paloalto Networks, so growth is still exceeding VMware's own expectations. I'd arrived at VMworld determined to know more about NSX, so this was encouraging to hear.

 
## vCloud Air
Then we see Bill Fathers take the stage to tell the story of VMware VCloud Air over the past 12 months, with particular emphasis on the past 9 months since it was announced in Europe another announcement about European expansion to come, he says. According to Bill, 2% of workloads were in the cloud 5 years ago and 6% now, but that growth is accelerating, a lot of it in the past year. Hybrid cloud solutions and vCloud Air are being designed to stop cloud adoption by the back door from the business. The aim is to put IT Professionals back in charge of the situation.
  
We then saw more video, about Betfair's adoption of vCloud air and news that there are now 3900 partners globally. Then the big news, the new German data centre is announced. As an interesting aside, the VMworld app that everyone is using here at VMworld is also running on VCloud Air. At least VMware do eat their own dogfood. Compliance, CSA, PCI and so on all tested and verified now, so this offering has grown up rapidly. It's also more flexible, as [VMware.com/go/ondemand](http://vmware.com/go/ondemand) is the new on demand access service where you can pay by the hour if you so wish. 

## Mobility  
Now Sanjay Poonen on stage, already the bloggers are checking watches and muttering about 11am sessions, with this keynote definitely overrunning again. Sanjay revealed that there is more software in your car than Apollo 11. Cars are being added to the usual images of desktop, laptop, tablet and phone in these VMware slides for this part of the presentation. Well, it's Tesla specifically it seems. Additional industry leading DaaS, horizon etc. services, the Google and Nvidia announcement again. Graphics abilities on laptops using the power of a data centre hosted compute resource. This is more stuff the same as the US keynote, along with the Horizon Flex announcement. Offline VDI for mobile users. 

Then more HP news, as they are also announced as a partner in the mobility space with Airwatch. Airwatch and Apple tied in with United Airlines to manage a lot of their processes. They mentioned baggage handling but also landing instructions on iPads! An interesting thought.
  
There was more content here, but I had an 11AM session I did not want to miss, so it was time to leave the bloggers space. You (like me) can catch up on the general sessions online though, at [VMware Now](http://www.vmware.com/now) and you can also get a more partner-centric view over at Gregg Robertson's [TheSaffaGeek blog](http://thesaffageek.co.uk/2014/10/15/vmworld-day-1/), particularly relating to some of the new announcements that I don't get to see in advance.

## Session: STO2197 - Storage DRS: Deep Dive and Best Practices

This was one of a number of sessions I had planned over the course of the week with a storage related angle to it. From a show of hands in the session, a lot of people use storage DRS, but not everyone wants to use it fully automated! There was a fair amount of centent here relating to the new features slated to come in the next release of vSphere. Let's suffice it to say that there will be more features, more controls, more integration than currently available in 5.5. (that shold be NDA safe). 

A lot of coverage was given to SIOC and how it integrates with VASA as well. If you're not using SIOC, you should be - but only applied at either the hypervisor level or the datastore level, not both! This depends on what storage you have, if you can use VASA, then use datastore level SDRS controls. I found this session really interesting as it's not something I get involved in every day, so a good start to the "normal" VMworld content.

## Session: STO2554-SPO - Zooming In: How Vmware Virtual Volumes (vVols) Will Provide Shared Storage with X-ray Vision

Probably taking the award for longest session title, here's further proof of my storage slant! Another one of the hot topics for this year, it was worth taking in a VVOLs session to see what all the fuss is about. This is more VASA based gubbins, basically you have a policy-driven control plane so you can focus on setting the storage requirements for each of your VMs and let vSphere worry about the rest for you in it's object storage format. The second half of this session was more of a 3Par sales pitch, they support VVOLs across their range, but at least had the good grace to say that other vendors do too, such as IBMs SVC and XIV storage.

You can find out more on VVOLs at the [VMware blog](http://blogs.vmware.com/vsphere/tag/vvols).  

 
## HoL Tour
I then managed to grab some lunch on the run, but there was not a lot left at this point as I was passing before rushing off to the Hands-on-Labs tour that was organised as one of the TAM exclusive sessions. This was really cool! Everyone who goes to VMworld knows about the HoL's. Most people take at least one. The opportunity to see how it all works was an insight worth taking and it turned out to be a really slick operation - not one second of downtime was experienced at VMworld in San Fran back in August. Here at VMworld Europe, it may be a smaller scale, but half of the lab sessions were running on EVO:RACK, the big brother to EVO:RAIL and half on UCS hardware. Quite a few of the labs are pre-spun up ready for punters to come and connect to them and before anyone gets near the setup, VMware run a script to load test the whole thing, it takes all the desktops and does stuff like turn labs on and off as fast as possible, push the manuals through the pages and so on, so they know it should stand up no matter what. There's a control centre and lots of monitoring screens, vRealize Operations Manager, Log Insight and so on, so they tend to see problems before those taking the labs experience it.

  


[![The HoL Monitoring screens](/img/20141019hol.jpg)](/img/20141019hol.jpg)

The Infrastructure Monitoring Screens for the HoL
 

## TAM Session
Next up was another TAM session, on the web client. This and the HoL tour were the only 2 TAM sessions I had confirmed before Barcelona due to me signing up so late, neither was top of my list (probably explains why there was space) but both turned out to be good! There was a lot more NDA stuff in here and a fair amount of honesty. Everyone knows the current web client is not good enough to replace the C# client as VMware wants and this session went over the next version and beyond, which was really insightful. I got to go in to the TAM Customer Central area for this session, which was a relaxed place! Sufficiently removed from the maddening crowds, with nice sofa's and its own coffee and cake. It was nice to refuel in there.  

## Parties
The day at the convention centre was still not over though, time to walk right to the other end of the site to the TAM Customer reception for some free beer and tapas. Then back to the flat to get ready for the night proper. I'd bagged an invite to the vExpert party from Eric Neilsen and Cory Romero (thanks guys!) and it was definitely worth me going, back to Ocana for this - a couple of hours to talk to folks who all have something interesting to say, ranging from vxdc001 down to me. Plus the waiter recognised me from last night, so there was plenty more tapas! I was flagging a little by this point but then I was convinced that attending the Veeam party would be a good idea. And it was. Standing on the beach at midnight, in a t-shirt, with a beer. Lovely. Thanks to Jane and Alex for talking me in to it, I wouldn't have seen Chris Dearden's jacket otherwise!
