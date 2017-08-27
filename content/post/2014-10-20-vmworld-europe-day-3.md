---
author: Dave Simpson
date: 2014-10-20 21:56:00+00:00
draft: false
title: VMWorld Europe 2014 - Day 3
type: post
url: /2014/10/20/vmworld-europe-day-3/
categories:
- Posts
- VMworld
thumbnail: "img/20140825vmworld.jpg"
description: "VMworld Europe 2014 Day 3"
tags: [VMware,VMworld,Community]
---

The final day, an early start to the sessions with no keynote to overrun into the first session, so I went straight into a 9am breakout session.  
  
## Session: INF2311 - vCenter Server Architecture & Deployment Deep Dive  
Some good tips here for the folks running (or planning to run) vCenter 5.5 specifically around the placement of vCenter components. Do not, do not, do NOT run your Inventory service on a different server to your vCenter server service! If you do, performance will be terrible. In fact, it's best to have the inventory service installed on different spindles to the rest of your vCenter server if you can manage that. That's how important this is. You know how you always get told to have a 100GB drive for vCenter? This is why, the Inventory Service has its own local database, separate from the vCenter DB and it will take up some GB's. This is also where your tags and storage profiles etc. reside, so back it up!  
  
If you want a single SSO domain, to keep the same vsphere.local and for linked mode, then you should look for sub 12ms latency between SSO servers. There are of course, reasons to spin SSO out from vCenter if you are running a whole lot of SSO based services, such as a vSphere 5.1, 5.5 and some vCAC. Then you need a load balancer and an HA setup, definitely a requirement if you want to run more than one SSO server with the same SSO site name, otherwise the SSO lookup services default to the first server built only. No point thinking you have redeundancy when you don't! But you'd test this out, wouldn't you?  
  
Then we also had a tech preview bit, I'm thinking some of this is still under NDA, so I'm not gonna say a lot here, other than to mention that the usual bigger, better, faster, more kind of thoughs are prevalent, as you'd expect when looking at whats slated for 6.0. Anyway, sign up for the beta and find out for yourself!  

## More TAM Sessions
In what had been a common thread for the week, it was then time to see if I could dump my scheduled sessions and attemd some more TAM briefings - again, the answer was yes. Two more TAM sessions then, one on ESXi 2016 and the other on Auto Deploy and Host Profiles, so they were even synergistic sessions (and the same presenter to boot). Both of these sessions went beyond 6.0 and again gave me a good insight in to the future roadmap. Of course these features may never all see the light of day, but it's good to see what's coming - it also gets you thinking about what else may be on the way. Worth skipping the "leet" EVO:RAIL session for? Definitely!  
  
There was a nice pallet of VMworld Alumni mugs dropped off outside the bag drop as well, I got one of those in time, pretty decent looking, let's hope it lasts me a little while, I'm not doing well with mugs at work right now.   

## Solutions Exchange and EVO:Zone  
After this it was time to take another run around the Solutions Exchange, mainly because I wanted to have a look at the EVO:Zone which I had been saving for the last day for some reason - I caught a presentation there and I also had a chance to have a chat about EVO:RACK as well as to see all the different vendor hardware in the "flesh". I'll be watching this with interest as things start shipping. Of course, all the vendors are desperate to give stuff away on the last day to save packing it to ship home and all the delegates are trying not to take on any more stuff since they are probably already overloaded, so that was somewhat fun. Some of the prize draws were also done at this time. The Nutanix Rolex's were won by a guy in a Dell shirt. I'll just leave that there :-)  

## Wrap Up
My last session was going to be the PowerCLI session, but I was done by then, my brain would not have kept up, so I will revisit that session another time online. Instead I chilled out for a half hour in the sun before the conference closed up. Then a quick hideout in TCC until the bag collection queues shrank and that was me done. Bus back to the airport, all done!  

Overall, I had a superb time. I'm pretty fortunate to be a member of the London VMUG, so I am blessed with a really strong local community, but VMorld was way bigger! I met so many interesting people, some for the first time, some I seem to bump in to wherever I go. At differing times I walked, talked, learned, ate or drank until I couldn't walk, talk, learn, eat or drink any more (not all at once though). I definitely made the most of it, I hope to do it all again soon.
