---
author: Dave Simpson
date: 2015-04-20 16:56:00+00:00
draft: false
title: VMware's April 20th launch of Photon and Lightwave
type: post
categories:
- Posts
thumbnail: "img/20150420photon.jpg"
description: "VMworld Releases Photon and Lightwave"
tags: [VMware,Photon,Lightwave]
---

  
Over the last couple of weeks there's been a lot of talk about products being launched by VMware's relatively new Cloud-Native Applications division. Now the launch date is here and even though it's not quite launch time yet, the cat is out of the bag.  
  
The products are currently known as;  
Project Photon - A stripped down Linux version optimised to run on the vSphere hypervisor which is designed solely to host and package containers.  
Project Lightwave - An Identity and Access Management (IAM) tool which ties in to existing  VMware authentication products.  
  
  
[![Photon Logo](/img/20150420photon1.png)](/img/20150420photon1.png)
  
[Photon](https://blogs.vmware.com/cloudnative/introducing-photon/?src=vmw_so_vex_dsimp_889) offers support for Docker, rkt (last time I looked, this was still called Rocket) and Pivotal's Garden container format. Since Photon is by VMware, for VMware, the hope is that existing enterprise customers will use this option rather than any other container platform, such as CoreOS, Ubuntu Core and the like. This is an open source development which is available from GitHub and more. The "selling point" for Photon is the vSphere optimisation which VMware say makes Docker containers run faster here than anywhere else. I have some Linux VM builds underway in my home lab which were destined to simply be a platform for Docker containers, so there will be an interesting comparison to be made here.  
  
There are 4 different installations of Photon that can be carried out, Micro, Minimal, Full and Custom. Full provides everything you need to package containers as well as run them, whereas Minimal, like the name suggests, provides the minimal requirements to run containers. Micro is literally just the Photon OS itself, and custom, well, you get the idea.  Installation is literally as simple as selecting the version, providing a hostname and root password. An installation of the Full version, followed by reboot and logon takes under a minute.   
  
There's a pretty handy [video on YouTube](https://www.youtube.com/watch?v=lHW795iSpNs) which demonstrates installing on Fusion and running Docker Configs afterwards.  
  
  


[![Lightwave Logo](/img/20150420lightwave.png)](/img/20150420lightwave.png)
  
[Lightwave](http://blogs.vmware.com/cloudnative/?src=vmw_so_vex_dsimp_889) offers enterprise level authentication and authorisation services for container related objects (containers, users, computers and so on) via username/password. tokens and certificates and as such, supports a number of well known standards, including OAuth, SAML, LDAP v3, X.509, SASL and WS-Trust.  
  
Clearly the two products being announced today are designed to fit together, with Lightwave providing photon containers with the ability to be locked down, segragated across environments, split multi-tenancy and so on - all governance and compliance related features which you would expect to see in a cloud infrastructure. Enterprise IT has a problem with containers in that they are easy to proliferate, widely available, easy to download but hard to secure and control. VMware are hoping that Lightwave will tackle this problem. Again this is an Open Source product and again, there's a [You Tube video](https://www.youtube.com/watch?v=CWmE_Rl3ELc).  
  
  
To go with all this Open Sourcery, VMware now has a [page on GitHub](http://vmware.github.io/),  
  
The full [VMware news release](http://www.vmware.com/company/news/releases/vmw-newsfeed/VMware-Introduces-New-Open-Source-Projects-to-Accelerate-Enterprise-Adoption-of-Cloud-Native-Applications/1943792) goes on to detail a number of partnerships which tie in with these releases. Pivotal have announced[ Lattice](http://blog.pivotal.io/cloud-foundry-pivotal/products/lattice-simplifies-container-clusters), which is able to expose a number of their Cloud Foundry services to Photon, for container scheduling, logging and the like. The idea here is that it provides a small footprint development environment suitable to start off on a developers laptop and able to scale out to within the cloud. Project Photon is already packaged as a Vagrant box, available through [HashiCorps Atlas](https://atlas.hashicorp.com/vmware/boxes/photon) and both Photon and Lightwave will be available through JFrog's [Bintray](https://bintray.com/) distribution platform as well. CoreOS provide rkt support within Photon and [Mesosphere](https://mesosphere.com/blog/2015/04/20/were-tackling-container-security-at-scale-with-vmware/) are talking about how they also work with Photon/Lightwave to provide scale via their DCOS.  
  

