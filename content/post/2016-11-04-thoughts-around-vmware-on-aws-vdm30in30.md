---
author: Dave Simpson
date: 2016-11-04 08:55:00+00:00
draft: false
title: 'Thoughts around VMware on AWS - #vDM30in30'
type: post
url: /2016/11/04/thoughts-around-vmware-on-aws-vdm30in30/
categories:
- Posts
- vDM30in30
thumbnail: "img/20161104vmwonaws.png"
description: "What will VMware on AWS mean in future?"
tags: [AWS,Cloud,vDM30in30,VMware]
---

It seems like everyone and his dog has written a post about this already, so here's mine.  
  
The biggest buzz at VMworld Europe was actually about an announcement that came out the week before, which is quite something, considering that a lot of nice announcements were made over the duration of the show as a whole. If you've been living under a rock for a while, [VMware](https://www.vmware.com/cloud-services/vmware-cloud-aws.html) and [AWS](https://aws.amazon.com/vmware/) are planning to co-operate so that by the middle of next year you can run your VMware VM's natively on the AWS cloud.  

Interesting that this was such a hype-fest, considering that it wasn't even a new concept. [VMware](http://www.vmware.com/radius/what-vmware-cloud-foundation-on-ibm-cloud-means-for-companies-globally/) had [IBM](https://www.ibm.com/cloud-computing/solutions/ibm-vmware/) on stage at VMworld Vegas earlier this year, announcing a joint venture, coming soon, which will enable VMware VMs to run natively on the IBM Cloud. The reaction to that seemed to generally be along the lines of  

> "OMG, VMware is Dead, Look at them getting into bed with a dinosaur of IT in a desperate attempt to stay relevant!" 

Enter Amazon, stage left, a few weeks later and everyone be like  

> "Aagh!! This is the best thing ever, look at that! VMotion into the Cloud, Elastic DRS! When can I buy this?? Get me in the Beta!"

That's two big clouds, regardless of your thoughts on one being a dinosaur and one being the dinosaur extinction event. Who is to say that this is going to stop here? Did you see the slides in the Europe keynote around Cross-Cloud Architecture, with the Google logo, with the Azure logo? No, I'm not suggesting that you're gonna be running VMware VMs on tin provided out of an Azure datacentre anytime soon, but you can see it with Google can't you? I didn't see Oracle anywhere, by the way.  
  
So, moving on, this is a fascinating concept, isn't it? You're gonna be using the [Cloud Foundation ](https://www.vmware.com/uk/products/cloud-foundation.html)platform in the cloud. Who'd have thought?! vSphere, vCenter, NSX, VSAN - all tied in to the blueprints that are [VMware Validated Designs](https://www.vmware.com/support/pubs/vmware-validated-design-pubs.html) and all updated and maintained for you, by VMware. That could be a double edged sword though, the updates will be faster and you may find yourself upgraded, like it or not. Plenty of potential for trouble there - you will have to scramble to keep your on-prem deployment in synch with your cloud deployment! Who is to say that this is going to stop here? More and more of the new vRA deployments VMware do are tied in with NSX. How long before you have vRealize built in to all of this as well? Automation, Orchestration, Chargeback. Kinda makes sense for a cloud, doesn't it?  
  
You may wonder about what that means for a variety of other partnerships and solutions that VMware have offered recently, namely EVO:SDDC and vCloud Air. Well, I don't know a lot about vCloud Air and we don't know what the pricing structure is going to be for VMware on AWS (or IBM) so I'm not in the best place to comment on whatever angst this may be causing, but I do know that there was a thing a few VMworlds ago about EVO:RAIL and the speed at which you could stand one up. Then there was an extension of that from a 4 node 2u device to a rack. EVO:RACK, with a suggestion that you'd wheel the thing into your datacentre and hook it up and after you turned it on, a couple of hours later you'd have a datacenter ready to go. This soon got renamed to EVO:SDDC and then, well, you know that EVO:SDDC's dead now right? It just got morphed into Cloud Foundation. You can stand that up in a couple of hours, sounds rather familiar.  
  
So everything that VMware's been up to in the last few years is all coming together, into an SDDC solution, which to be fair, is what they said they were going to do all along. Put this on Amazon bare metal with access to all the other Amazon services and you might have all the cloud you need.  
  
Use cases? Numerous.  

  * No need to re-engineer all that legacy application stuff to get yourself in to the cloud. You can natively move your VMs right in if the kit they're running on is looking a bit tired next year. Using vCenter, not some other API / front end that you don't know inside out already. 
  * You can set up a DR site in AWS in no time at all. As long as you have a few hosts to build a VSAN cluster and host your SRM placeholders, then if you need to push that big red button and invoke DR, you can take advantage of Elastic DRS and provision out the rest of your cluster right when you need it the most. 
  * Add in the usual stuff about quick copies of an environment that you need for a few hours to prove out an upgrade or whatever
  * Burst out into the cloud if you need to to meet high demand where half your cluster is sat up in Amazon (or IBM) with an affinity rule keeping your VMs on site by preference if that's what you want. 
  
There's a lot of possibilities here.    
  
Cost?  
Well, "Compelling" says VMware CEO Pat Gelsinger, let's see if that's the case. It'll also cost to get data in and out of a cloud, after all.  
  
The Market?  
Stock market, that is. VMware's share price is on the up after this announcement. Sometimes the market knows best, sometimes everyone just jumps on like one lemming after another.  
  
Assuming this goes as planned and the offering does indeed come out in the middle of 2017, then I am very, very interested to have a look at it, yes, I have signed up for the [Beta](http://learn.vmware.com/37941_REG) already. I also feel that this development is gonna drive a whole load of VMware admins to take a look at AWS as well, which is never a bad thing. After all, you can't stop learning...
