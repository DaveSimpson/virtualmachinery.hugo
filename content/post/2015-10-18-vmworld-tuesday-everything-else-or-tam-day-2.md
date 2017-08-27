---
author: Dave Simpson
date: 2015-10-18 13:02:00+00:00
draft: false
title: VMworld Europe 2015 Tuesday - Everything else (or TAM day 2)
type: post
url: /2015/10/18/vmworld-tuesday-everything-else-or-tam-day-2/
categories:
- Posts
- VMworld
thumbnail: "img/20151013vmworld2015train.jpg"
description: "VMworld Europe 2015 "
tags: [VMware,VMworld,Community,TAM-Customer-Central] 
---

## TAM Session - ESXi Lifecycle
I was straight off to the first of my TAM sessions after the general session, covering the ESXi lifecycle. The basic gist of this one is that VMware recognise that customers find it time consuming to maintain hosts and possibly difficult to spin up hosts. There's one tool to provision (auto deploy), another place to go for initial configuration (host profiles) and then another to manage going forward (VUM). Discussions centred on initially not having the majority of this process even available from the web client on through where we are now, what is coming next and then on to the more distant future. I have been asked not to post full details here as a lot of what was covered is subject to significant change over time, so let's just say that the move is towards accessibility from the web client and, significantly, a drive towards faster turnaround times and much less disruption when hosts are being patched in future. This is starting along the lines of intelligent placement of VMs when a cluster is being patched to minimise total vmotions through to more complex matters.  

## TAM Session - V2D
The newly announced V2Ds (VMware Validated Designs) was the next TAM session and this discussion saw as many VMware staff in the room as there were customers, which allowed us to get a range of views from different angles on the V2D process, which is something that VMware have been developing for a while now, has been used internally to assist in the development and integration of the fleet of products being announced at the moment and is soon to be released on the rest of us. The common look and feel within the CMP platform, the move to simplicity and better integration are all good design ideals which are hopefully going to make a difference to the way products get used. If VMware have their way then it seems that a lot of their products will be used in these designs (surprise, surprise!). Even the Foundation level of the V2D docs contains the likes of NSX and vRA. Check out the [V2D Feature Walkthrough here.](https://featurewalkthrough.vmware.com/?_escaped_fragment_=/vmware-validated-designs)  
  
On that note, VMware are still pushing NSX very hard and again it was the top ranked Hands on Lab session every day this VMworld. Lots of people who I spoke to across the week want to know more about it, very few actually have their hands on it.  

## TAM Session - vRA 7.0  
My third TAM session  of the day covered the newly announced vRA 7.0.The new vRA looks a lot slicker, has a smaller footprint, looks like it should actually install without too much agrovation (which will be a massive plus compared to 6.x) and install a lot quicker too. It does still need some windows services (IIS/SQL) but you can go down to as few as one appliance, which is nice. From what I have seen, installation takes a bunch of parameters upfront, goes as far as to install SQL for you, waits for ports used by other parts of the installation to be recorded in the database and then passes those port numbers to different parts of the installation as required, so it seems that some harsh lessons have been learned here. I actually now look forward to taking a go at installing this when it becomes available. Once everything is installed, further improvements follow, such as the automated import of templates into (new) unified blueprints, which gets you started faster too. The unified templates will make things easier to navigate as well, the canvas seemed logical to me and there's an easy visual guide to where you place components, since they turn red if they don't fit where you are trying to put them. For instance, if you have a VM on your canvas and have an SQL application on it, you cannot drop a db creation script in next to the sql app, it has to be placed on top of the app, to be nested properly.

[![The New Canvas and nested constructs](/img/20151018bpcanvas.png)](/img/20151018bpcanvas.png)

_An example of the new canvas and the nested constructs I mentioned above, definitely in the public domain as this is from the VMware blog site. _  
  
We also get to use vIDM, VMware Identity Manager in the new release, SSO is all well and good for your vSphere management, with it's limited number of users, but vIDM is designed to be something that scales through thousands of users. It also handles multiple domains and multiple tenants. Some other features that caught my eye were the much tighter integration with NSX in this version and the new control centre with embedded vRO 7.   
  
A fuller list of what you get with the new version has been [compiled by Sam McGeown](http://www.definit.co.uk/2015/10/vmworld2015-vrealize-automation-7-briefing-notes/), who knows the product a lot better than I. Jad El-Zein was a busy guy that day, since he ran a vExpert session first off and was then in our TAM session as well. You can see more on vRA 7 at the [VMware Blogs](https://blogs.vmware.com/management/2015/10/vrealize-automation-7-0.html) site.  
  
## Hang Space  
Time for the Hang Space and the Solutions Exchange after this, since quite a lot of vendors were on my list to talk to. Some companies were more willing than others to talk over the recent happenings in the storage space, by which I mean the Pure IPO as well as that Dell/EMC thing. This did seem to be a show dominated by storage one way or another. VMware themselves did cover VVols and VSAN in some detail in a range of sessions, probably two thirds of the main sponsors had storage to sell you of one variety or another. Always good to get a feel from the vendors themselves about who's up, who's down, what partnerships there are out there, that type of thing. Before I went to VMworld I was pretty sure that the Dell rumour was going to start of a wave of acquisitions, now I am only more convinced of that. Some vendors out there appear to have a nice ranked list of who they are hoping to be acquired by!  

There's always some swag to collect too, in return for all those delegate badge scans which mean I will have to leave my work phone on forward to voicemail all next week. I was at the show more in my capacity as a vExpert than in a corporate role, so I had absolutely nothing I wanted to seek out to consider buying (sorry vendors!). Best grab of the day had to be the Simplivity vExpert hoodie, especially since the weather had taken a turn for the worse and there was the small matter of the Veeam party to attend that night.  
  
## Veeam Party
Hmm, the Veeam party, lots of people have this party as the highlight of their week, there's always a queue, so it was good to see that I was definitely on the list to get in, despite not having received a QR code. I met a huge number of people at the party, there were some sights to see there, not all that agreeable, but I will leave you with this one...  

[![Me and the fella who taught me VMware back in the day](/img/20151018veeam2.jpg)](/img/20151018veeam2.jpg)

_Pictured with my VMworld Europe partner in crime, the inimitable [@rickyelqasem](https://twitter.com/rickyelqasem)_

  
  
  

