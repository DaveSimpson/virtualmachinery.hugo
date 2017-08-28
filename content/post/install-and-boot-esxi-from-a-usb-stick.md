---
author: Dave Simpson
date: 2014-07-03 00:35:00+00:00
draft: false
title: Install and Boot ESXi from a USB stick
type: post
categories:
- Posts
thumbnail: "img/20140703motherboard.jpg"
description: "Links for where I went to find out how to boot ESXi off a USB stick"
tags: [VMware,vSphere]
---

An increasing number of motherboards these days have USB sockets built in, which makes it very easy (and cheap) to run an ESX host, without having to obtain any local DAS storage. Good for the home labber, also good for the corporate guy who's boot-from-SAN usually.  
  
There's no point re-inventing the wheel here, since there are already blogs out there that talk you through the entire process - like this one from Brian Graf at vtagion;  
[http://www.vtagion.com/boot-esxi-usb-flash-drive/](http://www.vtagion.com/boot-esxi-usb-flash-drive/)  
  
He's also got the get-out for when you are finished with the USB key as well, since Windows only shows you the installer / ISO image size not the full size of the USB key, if all you have done is use the USB key to install to local disk, which for windows users like me, leverages diskpart;  
[http://www.vtagion.com/reformat-bootable-esxi-usb-flash-drive/](http://www.vtagion.com/reformat-bootable-esxi-usb-flash-drive/)  
  
Whilst writing this, I thought I would have need of this for a quick install job, but it turned out that I didn't. However, this is a good-to-have-in-the-back-pocket setup which is just the sort of thing I can blog about for posterity or maybe it will even help someone else?
