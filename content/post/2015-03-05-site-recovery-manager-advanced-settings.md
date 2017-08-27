---
author: Dave Simpson
date: 2015-03-05 18:02:00+00:00
draft: false
title: Site Recovery Manager Advanced Settings
type: post
url: /2015/03/05/site-recovery-manager-advanced-settings/
categories:
- Posts
thumbnail: "img/20150326srm.jpg"
description: "VMware vcenter SRM Advanced Settings"
tags: [VMware,SRM,vCenter]
---

At this point, I am not going to go in to detail about the installation of SRM 5.x, as there are already lots of good blog posts / series out there about this. SRM 6.x though, fair game!  
  
However, I wanted to lay out some of the changes that should be made after an installation of your SRM environment before you start your testing, to give you the best chance of success as possible.   
  
These are settings from SRM 5.5 / SRM 5.8 and work with the IBM SVC SRA's.  
Some of these I got from the consultant who helped me set up my first SRM installation a few years back, Bob Greenway, some are sourced from the web and some from my own testing or bitter experience. I've found the blog that helped me way back when - [Virtualization Blog - By Munishpal S Makhija](http://vcommunique.blogspot.co.uk/2013/06/best-practices-vmware-srm.html)   
  
To make the changes, you need to visit all Protected Sites and your Recovery Site from the Sites menu in SRM and under the right click menu you can see "Advanced Settings..." Click this.  

The following SRM settings should be changed from defaults.

| option | Setting |
| ------ | ------ |
| recovery.customizationTimeout | 1800 |
| recovery.powerOnTimeout | 1800 |
| storage.commandTimeout | 30000 |
| storageProvider.autoResignatureMode | 1 |
| storageProvider.fixRecoveredDatastorenames | ticked |
| storageProvider.hostrescanrepeatCnt | 3 |
  
  
And the reasons why:

  1. If you customise VMs on recovery, then you don't want this operation to time out

  2. Wait longer to get a response from VMware tools from slow starting VMs.

  3. SRM needs more than the default time to map storage 

  4. With this setting, SRM resignatures all known VMFS snapshot volumes, including any volumes that SRM does not manage
  5. Removes the “snap” names from the start of recovered datastores
  6. Additional scans from ESX hosts to find all the newly mapped datastores never hurts

#### Addendum:

Subsequently I'd seen a problem with SRM database connectivity which required me to make the following changes; 

Edit the following file and amend 2 values from default  
C:\Program Files\VMware\VMware vCenter Site Recovery Manager\config\vmware-dr.xml   
Change the value from 5 to 10 to increase the size of the pool of database connections   
Change the value from 20 to 30 to increase the maximum number of database connections  
Restart the VMware Site Recovery Manager service

This is also an option you can amend during the SRM installation. 
