---
author: Dave Simpson
date: 2017-08-29T16:48:50+01:00
draft: false
title: 'VMworld 2017 Tuesday General Session'
description: ""
categories:
- Posts
- VMworld
tags: [VMworld, VMware]
thumbnail: "img/20170829session2.png"
---

Settling in for another stream from the VMworld.com site. The day 1 General Session came with a whole bunch of new announcements, plus some that didn't even get a mention, so what will today's bring? Here comes Pat Gelsinger to tell us.

A brief intro and then the introduction to Michael Dell, who is, in case anyone didn't know, Chairman of the Board of VMware, for some live Q&A. 

## Fireside Chat

[![A Cozy Chat with Pat and Mike](/img/20170829chat.png)] (/img/20170829chat.png)

Firstly, Pat mentioned questions around support and response time. Pat asks for feedback at my.vmware.com if you're not getting your expectations met. Questions around the length of time it takes to get a response and expressed his dissapointment that this is an issue, so it looks like he will be doing something about this. Skyline (the proactive support solution) is one of the initiatives they are already bringing in to address this 

Next, AI developments. Michael says that the cost of making something use IoT is approaching zero, so the possibilities out there for AI in the future are tremendous. Dell Technologies is thinking a lot about Big Data as the backing for AI and Machine Intelligence. Even the best algorithms in the world need data to feed them. Michael talks to CEOs and says if you're not thinking about AI, then you're doing it wrong. Massive compute and data are enabling machine learning. Like yesterday, Pat mentions "Tech leaving the nest". 

> Today is the slowest day of technological development in the rest of your life!

Pat Gelsinger

Next - Autonomy. Most stuff is generated where most people work - small and medium enterprises, but the combination of companies that make up Dell Technologies also provide a lot of scope for growth. Michael tells us to be prepared for masssive growth at the edge of your network"

Ecosystem - Open ecosystem partners are a key part of VMware's continued success and Michael re-iterates his commitment to that. 

> The open ecosystem continues to grow and be very vibrant. 

Michael Dell

Laughs from the audience as after mentioning that Dell allows VMware to partner with Dell's rivals Pat admits that some of Dells partnerships may not make him as comfortable as he'd like, but that's OK. The synergy between Dell and VMware on VXRAIL gets a mention, as it is currently running at 400% annual growth. 

Now we get an announcement - Rob Mee, the CEO of Pivotal joins the guys on stage, he's got trainers on, he must know how to write code. A quick recap on the last 4 years first - PCF is in use in 50% of the Fortune 500. Last November, Pivotal partnered with Google to make Kubo. Now we see PKS - Pivotal Container Service. It will always contain the most recent version of Kubernetes, incorporate NSX. 

[![PKS](/img/20170829pks.png)] (/img/20170829pks.png)

Now also on stage Sam Ramsay from Google Cloud. He definitely codes, he's in a t-shirt. Container adoption is growning, Kubenetes is a really fast moving and fast growing open-source product and it's merging in to 
Google have been running containers for 13 years, supporting GMail, YouTube etc. They're now sharing this with Google Container Engine (GKE) which explains the K for Kontainer in PKS. 

[![PKS](/img/20170829pkslineup.png)] (/img/20170829pkslineup.png)

Google, Amazon and Apple have all been on stage at VMworld this year. Interesting times!

Pivotal and VMware are announced today as platinum members of the [Cloud Native Foundation](https://twitter.com/CloudNativeFdn). You can read more about the release of PKS at [blogs.vmware.com](https://blogs.vmware.com/cloudnative/2017/08/29/vmware-pivotal-container-service/)

## Now the meat of day 2!

So apparently, that first bit was just the warm-up act. Pat introduces Ray O'Farrell, VMware CTO "the certified smart guy of VMware". 

[![Ray](/img/20170829ray.png)] (/img/20170829ray.png)

The VMware approach is to make it easier for you to consume the technologies of today. Quite a few of the products announced this week are "as a Service" and are developer friendly. We move on to a whole bunch of demonstrations of VMware products at a fictitious company called Elastic Sky Pizza.

[![Elastic Sky](/img/20170829elasticskypizza.png)] (/img/20170829elasticskypizza.png)

A nice entertaining Pheonix Project type reference in this video, as an employee in IT suddenly becomes VP as someone quit. The focus soon shifts though on to what VMware products can be used to solve the issues outlined (which was basically everything's gone wrong, bad app, data leaks, you name it).

Enter [Purnima Padmanabhan](https://twitter.com/PPadmanabhan) and [Chris Wolf](https://twitter.com/cswolf) - Globally Consistent Infrastructure as Code is what VMware tell us is the answer to te problems seen be Elastic Sky. VMware Cloud infrastructure anchored by VMware Cloud Foundation is just the place to start to gain a consistent platform. 

[![All Cloud Architectures have their place](/img/20170829cloudarchitectures.png)] (/img/20170829cloudarchitectures.png)

A demo of AppDefense followed, with it discovering behaviours around the Elastic Sky pizza app - verify each of the applications in use based on the ports that they want to use and monitor the unknown threats as well, since AppDefense always looks for anomalies and flags them up. Then a demo of vROps showing datacentres with issues - complete with that link to VMConAWS so they select a region and roll out a bunch of extra servers, simple. Roll over to vCenter and there's your new VMConAWS cluster right next to your on-prem. To retain PCI compliance, move some less critical apps to the cloud. vRealize Network Insight will help you to do this. 

[![Elastic Sky](/img/20170829vrni.png)] (/img/20170829vrni.png)

Pick a green (easy to move) target and do a what if analysis before migration. Then into vRA, as this was a vRA deployed application, Day 2 actions will let you move the application into the cloud via vMotion. All covered by Appdefense to secure it. That's a compelling story.

> vSphere 6.5u1 is the fastest adopted VMware ESXi release in history.

Ray O'Farrell

More video commentary follows, Devs vs Ops. I read this in a book once. But here's a plan to fix it.

[![Elastic Sky](/img/20170829techpreview.png)] (/img/20170829techpreview.png)

Building a Kubernetes cluster - pretty fast. Building pods in VMware PKS lovely. Integration with vRA, looking good. 
into NSX using NSX CLoud.

[![NSX CLoud](/img/20170829nsx.png)] (/img/20170829nsx.png)

You need to utilise these features to manage the networking services running in AWS. Next using Wavefront to correlate issues arising, total order rate dropping, registration timeouts growing. Then (almost as an aside) you can have integration with Workspace ONE to deal with tickets from a mobile etc.

"Troubleshooting" continues and we are shown the actual code that has an issue and which geo it is located in, with an actual map of utilisation, rather than some big or little red or green squares. This definitely makes it more "real" for people. Time for a call to the provider with the issue to get it resolved. So we went all the way from infrastructure problems to application issues to resolving issues in the cloud. 

VMware [Workspace ONE](https://www.vmware.com/uk/products/workspace-one.html) is now available and a trial is open to everyone.

Fantastic integration between these applications, but still quite a lot of applications to introduce to get all of this working, which is not going to be an easy thing to do. Of course, no-one is going to implement all of this in one go, it may be a new corner case which gets additional integration first. but VMware did ensure to mention that in the keynote yesterday.

## The Future
An AI future with Pulse Iot Center and pizza trucks taking pizza to your door, cooking it en-route. Each truck is also equipped with a huge range of sensors, monitoring inventory in each truck as pizza's are being cooked on the way to the customers and hence you'll need to know when and where to re-up.

[![Faas](/img/20170829faas.png)] (/img/20170829faas.png)

Faas Event Sources - the sensors on a truck, weight sensors for each item.
Then set up tickets automagically when you are low on a particular inventory item. 
A map with your active truck inventory, interactive, using the open source Clarity interface, they built a UI to allow you to interactively query inventory on each truck. These queries are running on ephemeral containers on top of vSphere infrastructure so they only exist for as long as the query takes. This is all running right on the edge of your network.

The keynote comes to and end when (as predicted on the twitters) an Elastic Sky delivery guy shows up. I hope there's really a pizza in that box, those 2 earned it!

That was a bit of a whirlwind, but a really good day two keynote , I didn't know where the time went, to be honest. An impressive tour and an exciting ride through a whole heap of VMware technologies, this vision of VMware as a company delivering the operating system for the cloud(s) is starting to take shape in front of us. 
