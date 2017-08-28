---
author: Dave Simpson
date: 2015-10-30 18:08:00+00:00
draft: false
title: Update SRM 5.8.0.1 to 5.8.1 ASAP if you use linked mode
type: post
categories:
- Posts
thumbnail: "img/20151030warning.png"
description: "Running into a serious issue with SRM 5.8.0.1"
tags: [SRM,VMware]
---

VMware have not shouted about this one as much as they should have, given the potential gravity of the situation. If you use linked mode to connect multiple sites and have SRM 5.8.0.1 installed, then you will not be able to run an SRM recovery when you have the sites disconnected. As in, when you are experiencing a disaster which you want to recover from as quickly and painlessly as possible, as in, precisely what you purchased SRM for in the first place, you're out of luck.  
  
So, if you are using SRM 5.8.0.1 and you have vCenters operating in linked mode, go away **_now_** and break linked mode. Now you're safe. You can always put linked mode back, after all. That's a lot easier than trying to put your DR site back when you cannot see the Recovery Plans you spent time creating and testing.  

For a more complete explanation of the situation and the workarounds, you should visit VMware's [KB2093902](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2093902&src=vmw_so_vex_dsimp_889) which provides you with two workarounds, but as I mentioned previously, this problem is also resolved in the relatively recently released SRM 5.8.1, as you can see in the [release notes](http://pubs.vmware.com/Release_Notes/en/srm/58/srm-releasenotes-5-8-1.html?src=vmw_so_vex_dsimp_889).  
  
So now you have linked mode gone, your DR will work again, so you now have some time where you can think about how quickly you can test the powershell script or get off that version of SRM, whilst worrying about change control and all that corporate stuff.  
  
When I ran in to this problem, testing a site isolation, the Recovery Plans and the Protection Groups disappeared from _both_ sites when they were isolated. Not just the recovery site.  

[![No Recovery Plans or Protection Groups at all](/img/20151030noplans.png)](/img/20151030noplans.png)
 
As soon as the sites were reconnected, the Recovery Plans and the Protection Groups reappeared on both sites.  
  
The powershell script is available right from the KB article, I downloaded it, but have not tested it out yet, I just broke linked mode as that was easier at the time. The script looks clever in that it builds you a list of your recovery plans on the fly and assigns them numbers so you just enter the plan you want to run and the type of operation you want to perform on it, (Recovery, Test, Reprotect etc.) but you are not going to get a whole lot of visual feedback on the progress of the plan, the script is just gonna end when it's done. I have found a picture of it running though, on [penguinpunk.net](http://www.penguinpunk.net/blog/vmware-srm-5-8-you-had-one-job/).  
  
So, clearly, the information is still there somewhere in the Inventory Database on the vCenter servers. It's not showing up in the SRM GUI, but the powershell script can still get to it.  
  
All my testing with SRM 5.8 does show the improvements that VMware promised speed wise are there. I've tested in a variety of situations now and have seen performance increases of anything from x2 to x3.5 when going from SRM 5.5 to 5.8.0.1 so if your Recovery Plan is still there, it doesn't half run quickly.  
  
Me testing the powershell may never happen, testing an update to 5.8.1 seems more likely. There's an interesting new bug in the release notes for that version, which I may want to take a look at, given that my test lab is now up at 5.8.1 on both sites, but then SSO appears to have crapped out and I can't reinstall it (that's a whole different story) so a new vCenter VM is going to have to appear. Anyway, that new error is this..  
  


**Connecting to an existing database and selecting the Recreate the database option when installing a new Site Recovery Manager Server instance for use with a new vCenter Server instance causes installation to fail.** Recreating an existing Site Recovery Manager database for use with a new instance of Site Recovery Manager Server and a new instance of vCenter Server causes installation to fail with the error _Failed to clear Inventory Service registration_. This problem occurs in the following scenario:   

1. You install a new instance of vCenter Server
2. You attempt to install a new instance of Site Recovery Manager to connect to the new vCenter Server instance
3. During installation of Site Recovery Manager, you select an existing Site Recovery Manager database from a previous Site Recovery Manager installation
4. You select the **Recreate the database** option

In this scenario, installation fails with the error and rolls back. 

**Workaround:** When installing a new instance of Site Recovery Manager Server to use with a new instance of vCenter Server, connect Site Recovery Manager to a new database instance. 
  
So now I wonder if I will even be able to connect up a new 5.8.1 installation with my existing data? More on that later.  
  
  
  
  
  

