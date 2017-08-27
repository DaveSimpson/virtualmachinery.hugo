---
author: Dave Simpson
date: 2015-12-09 17:31:00+00:00
draft: false
title: vSphere 5.5 u3b released December 8th - plus other VMware releases
type: post
url: /2015/12/09/vsphere-5-5-u3b-released-december-8th-plus-other-vmware-releases/
categories:
- Posts
description: "VMware release a bunch of patches for vSphere 5.5 and a range of other products."
tags: [VMware,vRealize,vSphere]
---

6 new ESXi 5.5 patches came out overnight. [Click here](http://pubs.vmware.com/Release_Notes/en/vsphere/55/vsphere-esxi-55u3b-release-notes.html) for the full release notes. Your post update 3 VUM baseline would now look like this...  
  

| Vendor ID | Title | KB Article | Fixes |
| ------ | ----------- | ------ | ----------- |
| ESXi550-Update03 | Update 3 Rollup package | | vSphere 5.5 Update 3 |
| ESXi550-201510401-BG | Updates esx-base | [KB2133825](https://kb.vmware.com/kb/2133825) | Resolves issue with snapshot consolidation/deletion |
| ESXi550-201512101-SG | Updates esx-base | [KB2135795](https://kb.vmware.com/kb/2135795) | Updates OpenSSL to openssl-1.0.1p |
| ESXi550-201512102-SG | Updates tools-light | [KB2135796](https://kb.vmware.com/kb/2135796) | Includes fixes released in VMware Tools 10.0.0 |
| ESXi550-201512401-BG | Updates esx-base | [KB2135436](https://kb.vmware.com/kb/2135436) | Fixes to resolve 37 individual PRs |
| ESXi550-201512402-BG | Updates ehci-ehci-hcd | [KB2135792](https://kb.vmware.com/kb/2135792) | Provides USB 3.0 support for modern chipsets |
| ESXi550-201512403-BG | Updates tools-light | [KB2135793](https://kb.vmware.com/kb/2135793) | Includes fixes released in VMware Tools 10.0.0 |
| ESXi550-201512404-BG | Updates lsi-msgpt3 | [KB2135794](https://kb.vmware.com/kb/2135794) | Resolves drives detection issue with multiple HBAs |

There's also a new vCenter 5.5 U3b as well, as [detailed here](http://pubs.vmware.com/Release_Notes/en/vsphere/55/vsphere-vcenter-server-55u3b-release-notes.html). Make sure your SRM 5.8 install is at 5.8.1 rather than 5.8.0.1 before upgrading vCenter and do vCenter before your hosts!  
  
  
## The other December releases:

[vRealize Code Stream Management Pack for IT DevOps 1.0.0](https://my.vmware.com/group/vmware/details?downloadGroup=VRCS-MP-VRA-100&productId=472)  
[VMware Software Manager - Download Service 1.3](https://my.vmware.com/group/vmware/info?slug=datacenter_cloud_infrastructure/vmware_software_manager/1_3)[vSphere Big Data Extensions 2.3](https://my.vmware.com/group/vmware/details?downloadGroup=BDE_230&productId=491&rPId=9646)[vRealize Hyperic 5.8.5](https://my.vmware.com/group/vmware/info?slug=infrastructure_operations_management/vmware_vrealize_hyperic/5_8)[Horizon View 6.2.1](https://my.vmware.com/group/vmware/details?downloadGroup=VIEW-621-ADV&productId=529&rPId=9776#errorCheckDiv)  
[Realize Operations for Horizon and for Published Applications 6.2.0](https://my.vmware.com/group/vmware/info?slug=desktop_end_user_computing/vmware_vrealize_operations_for_horizon_and_published_applications/6_0)  
[Mirage 5.6](https://my.vmware.com/group/vmware/info/slug/desktop_end_user_computing/vmware_mirage/5_0)   
[Horizon Flex 1.6](https://my.vmware.com/group/vmware/info?slug=desktop_end_user_computing/vmware_horizon_flex/1_6)  
[Fusion 8.1.0](https://my.vmware.com/group/vmware/details?downloadGroup=FUS-810&productId=527&rPId=9750)   
[Workstation Pro 12.1](https://my.vmware.com/group/vmware/details?downloadGroup=WKST-1210-WIN&productId=524&rPId=9755)   
  
  
  
  
  

