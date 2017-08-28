---
author: Dave Simpson
date: 2017-08-28T16:51:40+01:00
draft: true
title: 'VMworld 2017 Monday General Session'
description: "Notes and background from the keynote presentation"
categories:
- Posts
- VMworld
tags: [VMworld,vExpert]
thumbnail: "img/20170828vmworld2017.png"
---
Rock and Roll! VR drawings and a Rock/cello mashup before Pat comes out to tell us that we should really be there in person. Well, I'll seeya in a couple of weeks...

A good touch to talk upfront about Hurricane Harvey and asking those watching to consider donating. 

The intial part of the keynote sees Pat talking about science fact in general, exoskeletons, "teleporting" atoms into space, Genetically modified organisms, driverless cars, even designing your own shoes online. But this change reflects the change in the way that life is changing. 100 years ago 80% of people were enganged in agriculture, now it is clearly way less. When I was a child, I read how we would all be people of leisure as robots carried out all the mundane tasks, but may be that it starting to happen with automation, rather than robot butlers for all.

[![VMware Cloud Services](/img/20170828agriculture.png)] (/img/20170828agriculture.png)

The Any App, Any Cloud Any device mantra from previous keynotes reappears. The edge, NFV, Automobiles are the new focus, the new frontier for VMware to move in to - presumably as well as being the OS for datacenters. In one of the early titbit announcements, Pat reveals that VMware IoT is now in beta at Toyota to built 'the connected car of the future'.

[![VMware Cloud Services](/img/20170828vmwarevision.png)] (/img/20170828vmwarevision.png)

Moving on to Workspace 1 Apps and Identity, Airwatch - VMware are now partnering with HPI. Dion Weisler, President and CEO of HP Inc. is welcomed on stage, announcing that VMware's endpoint management system (Airwatch) will be [incorporated into the HP 'Device as a Service' offerings](https://t.co/ugcB1ou4Gu). 

Then we cut over to the interview corner, with Sanjay Poonen and Jennifer Manry, VP of EUC at Capital One. Capital One have become another company to adopt the "we're a tech company that also offers x" approach of DevOps transformation. They hired literally thousands of developers to go agile.

Pat takes us back to the time he ran Intel and VMware came to see him to talk about Virtualisation. Haha love that "First VMware sales meeting" film, with [@herrod](https://twitter.com/herrod "still got it")  rocking it. 

[![VMware Sales Pitch](/img/20170828herrod.png)] (/img/20170828herrod.png)

I guess you can't really say "What the Fuck, No way!" on a stage that big, but you can watch someone on video say it when there's a soundtrack playing over the top of it. This video is definitely one of those things that will have made people smile. I used to have to submit change requests for vMotions until one day a vMotion brought a key server back online in seconds, that really was a "no way!" moment for folks who worked with me at the time. 

There are also some interesting announcements around the VMware / DellEMC platforms next. [VMware Cloud Foundation 2.2](https://docs.vmware.com/en/VMware-Cloud-Foundation/2.2/rn/VMware-Cloud-Foundation-22-Release-Notes.html) was released the other day. I really like cloud Foundation, you should be thinking on how to move your company (and yourself) up the stack, spend more time vbusting silo's if you have to spend less time dealing with hardware when someone else can deliver it to you as a commodity. 

[![VMware Cloud Foundation](/img/20170828cloudfoundation.png)] (/img/20170828cloudfoundation.png)


vSAN now has 10,000 customers, a count that is growing at over 100 a week, with 12 server partners, 2 OEM partners and 250 separate SKU's for vSAN Ready Nodes. Impressive growth. They are really pushing this and also Pat mentioned that VXRAIL is now the biggest selling HCI brand. A massive change from the days of EVO:RAIL a few short years back. I guess if you are confident that your idea is right, you regroup and you go again.

## VMConAWS goes live
Here's Andy Jassy @ajassy (AWS CEO) on stage at a VMworld something that I never thought that I would be writing, but here we are. It seems like a no-brainer, getting these two companies together when you think about it. Customers didn't want the polarity of running workloads solely on-premises or in-cloud offerings, you really can get the best of both worlds if you adopt something like VMConAWS or utilise the existing partnership with IBM.  
There's a lot of system integrators and other tech partners behind VMConAWS and a number of impressive customers already using it. 

[![The VMConAWS ecosystem](/img/20170728vmconawsecosystem.png)] (/img/20170728vmconawsecosystem.png)

Initially, this is only available in the US West (Oregon) region, but the aim is to have this available globally by the end of next year. US West and Europe are high up on the list.

There's also a HoL for this, HOL-1887 at VMworld. I imagine that one will be pretty popular!

Read the [VMware Press Release](https://www.vmware.com/company/news/releases/vmw-newsfeed.VMware-and-AWS-Announce-Initial-Availability-of-VMware-Cloud-on-AWS.2184706.html "VMware and AWS Accounnce Initial Availability of VMware Cloud on AWS")
also [the announcement from AWS](https://t.co/tCPvbBqQS9)

## VMware Cloud Services
Today the first 7 services are announced 
[![VMware Cloud Services](/img/20170828cloudservices.png)] (/img/20170828cloudservices.png)

Back to Sanjay with Karine Semmer, Head of IT Hosting Transformation & Modernisation Program at Medtronic. They're clearly a massive MedTech company, with many devices out in the world being used to save lives, so this really is critical at the point of delivery. 65 Million people benefit from a Medtronic device. They are adopting Cloud Foundation and VMConAWS it seems. 

Nice to see a Women in Tech focus, mentiond as a part of this interview - it had just been picked up by bloggers that we'd had two customer conversations on stage and both were with women and then the conversation moved to this specifically, Which is good. Still a long, long way to go until we don't have to mention this any more, of course.

## NSX
Pat is saying that across the next decade, NSX will be what vSphere has been for the past decade or two, the core focus of what they're doing. He suggests that if you're not using it, you are already behind. Well, if you are using the VMware infrastructure at any scale, then that is starting to ring true.

[![The Reach of NSX](/img/20170828reachofnsx.png)] (/img/20170828reachofnsx.png)

Next up, Matthew Nikolaiev from Sysco is in on stage in conversation with  Sanjay. "Talking to the real Sysco about networking" he says - now, now ;-) Sysco are the largest food distributor in the US and also have a global reach, apparently. Interesting stuff though, Matt said he span up a datacenter in 4 hours whilst lunching and attending meetings, that's impressive no matter who you look at it. Not the sort of thing that you'd do casually I guess, but interesting that it can even get mentioned like it was nothing.

Furthering the NSX news, [NSX-T 2.0 ](https://blogs.vmware.com/networkvirtualization/2017/08/nsx-t-2-0.html/) has been announced. 
> NSX-T as a platform has been purpose-built to be ready for IaaS providers to provide self-service functionality to their users.

## AppDefense
Pat brings up a very busy slide of the security industry. 

[![All those Security Vendors](/img/20170828securityvendors.png)] (/img/20170828securityvendors.png)


Then he tells us that the Tech industry has failed their users when it comes to addressing security. There needs to be a rethink where standardisation and back-to-basics approaches make the security options more transparent and more simple to implement. Sounds like a sales pitch, wonder what he has in mind?   

5 Pillars of cyber hygiene - white paper coming out today. Sticking to these basic principles will make us all safer. The claims are that 90% or attacks would be thwarted by adhering to these basics.

[![Five Pillars of cyber hygeine](/img/20170828fivepillars.png)] (/img/20170828fivepillars.png)

The compute stack hasn't yet been used to chase down security issues, or "Chasing Bad" as Pat says. I get the feeling that AppDefense is going to be this thing.

[![Five Pillars of cyber hygeine](/img/20170828appdefense.png)] (/img/20170828appdefense.png)

AppDefense whitelists intended applications and methods, developing this as it goes along. There's a capture, Detect, Respond 3 pillar approach. The key here is that there should be an automated, orchestrated response to threats as they arise. Puppet was mentioned as a partner and also IBM on stage to discuss further. 

> AppDefense is for compute what microsegmentation was for networks.

There is already a [VMware Lightboard Video](https://www.youtube.com/watch?v=HiJgn6GGX5w&feature=share) on AppDefense, which explains it better than I can, so watch this instead. Or you could read the [press release](http://ir.vmware.com/overview/press-releases/press-release-details/2017/VMware-Transforms-Security-for-Applications-Running-on-VMware-vSphereR-Based-Virtualized-and-Cloud-Environments/default.aspx). 

Dave Bullamore, VP IT End User Services at The American Red Cross is now on stage, poignant given what's going on right now in Texas and the south, but the focus does move back to technology. Mobility is important here and again, we are talking about peoples lives. Also a nice focus on smoke alarms and giving blood. Also, 30,000 people are expected to be in American Red Cross Shelters after they got to everone they need to after hurricane Harvey. 

Sanjay presents us with what he sees as the 3 top CIO Priorities - Cloud, Mobile and Security. 

[![Three CIO priorities](/img/20170828ciopriorities.png)] (/img/20170828ciopriorities.png)


## Customer Focus
There are 200 customers presenting at VMworld this year (a record) Sanjay would like to see that double for next year. 

