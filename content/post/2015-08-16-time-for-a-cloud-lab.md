---
author: Dave Simpson
date: 2015-08-16 21:04:00+00:00
draft: false
title: Time for a Cloud Lab
type: post
url: /2015/08/16/time-for-a-cloud-lab/
categories:
- Posts
thumbnail: "img/20150820ravello.png"
description: "First look at deploying VMs into the Ravello cloud offering for vExperts"
tags: [vExpert,Ravello]
---

Those lovely people over at [Ravello Systems](https://www.ravellosystems.com/) have given all of the current vExperts access to their nested virtualisation offering, so each month I have some free hours to run the equivalent of a homelab, but it's located somewhere out on AWS or Google, fronted by the clever Ravello interface. This should allow me to test out a whole bunch of things that are difficult to set up on a home lab, so I can keep the on premises stuff for running my production and put my dev / test in the cloud. I kinda think that's the idea isn't it?  
  
So I signed up to create an account, waited for my vExpert status to get verfied and then installed the image uploader that Ravello provide you with. If you simply cannot wait any longer to work out how this all works, then you can find out more about the upload process in the blog post that Ravello have already kindly made for you. [https://www.ravellosystems.com/blog/upload-iso-image-ravello/](https://www.ravellosystems.com/blog/upload-iso-image-ravello/)  

To start this off, I will need to upload a number of items up to my new library so I assembled things I guess I would need up in the cloud;  

  * vCenter Appliance 6.0
  * ESXi 6.0
  * Windows  7
  * Centos 6.7
  * OpenFiler
  * NSX
  
This is as simple as clicking on the library icon which is visible in the Ravello interface as soon as you log in;  

[![The Ravello Library](/img/20150816rav101.png)](/img/20150816rav101.png)

Here you can see some of my files actually uploading, There's also a few images made available for you from the get-go, as you can see from the bottom of the image. 

To import something, simply click the big orange Import Disk Image button and then log in to the disk import tool (which is simply logging in again, using your Ravello logon) you click anothre button to say you want to upload something and then get presented with the following list of options;  

[![Upload Options](/img/20150816rav102.png)](/img/20150816rav102.png)
 
So there we have it, the list of options and file formats available, along with the offer at the bottom to talk to them if you wanna use something different.  

The NSX image is in ova format, so I needed to extract the ovf and vmdk files from it to allow the Ravello interface to upload them. (ova is not supported - it's not really needed). Still, you need something to get the files out and I use 7-zip on Windows. Other archiving tools area available. There's a really step by step guide available [here](http://www.simplehelp.net/2015/08/11/how-to-open-tar-gz-files-in-windows-10/) - although if you're reading this blog post, I doubt that this is new to you.  
  
So, that's a start, getting the stuff in place to get building. that will come next.  
