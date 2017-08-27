---
author: Dave Simpson
date: 2016-03-17 23:06:00+00:00
draft: false
title: Upgrading to vCenter/ESxi 6.0U2
type: post
url: /2016/03/17/upgrading-to-vcenteresxi-6-0u2/
categories:
- Posts
thumbnail: "img/20160317vsphere6u2.png"
description: "Upgrading to vCenter/ESxi 6.0U2 in the homelab, from the CLI"
tags: [vCenter,vSphere]
---

They're fresh out, they contain a whole load of enhancements, and if you're a vExpert or enthusiast running a homelab, then you'll most likely want to get a look at the new vSphere 6.0 Update 2 stuff ASAP.  
  
Time to quickly upgrade the vCenter Appliance and ESXi hosts to take advantage of the HTML5 interface, built in Host Client, VSAN 6.2 and so on. This is assuming you're not an enterprise with enterprise ways and means, of course...  
  
  
  
## Upgrade vCenter 6.0 Appliance to Update 2 (build 3634794)
1 - Visit the [product patches](https://my.vmware.com/group/vmware/patch#search) page at my.vmware.com and download  the zip file VMware-vCenter-Server-Appliance-6.0.0.20000-3634791-patch-FP.iso (and [see the notes](http://kb.vmware.com/kb/2138600) whilst you are at it)  
2 - Mount the above iso to your VCSA Appliance and ssh in to the appliance  
3 - At the Command> prompt, issue the command 

    software-packages install --iso --acceptEulas
4 - Watch the install proceed - this will take a while, so why not start the next bit for your hosts?  
[![The upgrade on the CLI](/img/20160317vc6_0_u2.png)](/img/20160317vc6_0_u2.png)

5 - Once finished, unmap the iso image and issue the command 
	
    shutdown reboot -r "Update 2"

## Upgrade ESXi 6.0 to Update 2 (build 3620759)
1 - Download the ESXi Offline bundle file from my.vmware.com and upload it to an ESX accessible datastore  
2 - Put your host in to maintenance mode  
3 - ssh in to the ESXi host and issue the following command  

    esxcli software vib install -d /vmfs/volumes//update-from-esxi6.0-6.0_update02.zip

4 - Watch the install proceed and then reboot when finished  
  
That's about it folks, have fun!  
  

