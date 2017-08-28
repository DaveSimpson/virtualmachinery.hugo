---
author: Dave Simpson
date: 2015-03-04 23:07:00+00:00
draft: false
title: vCenter 5.5 and SRM 5.x Services on Windows Server 2008 failing to start
type: post
categories:
- Posts
thumbnail: "img/20151030warning.png"
description: "vCenter and SRM Service startup problems"
tags: [vCenter,VMware,vSphere]
---

A few oddities I have discovered recently when working on one of my lab environments, so I thought that I would note them here for my own ends if nothing else.   

It is possible that a Windows Server based vCenter 5.5 (in my case) will not start after a reboot with the error message in vpxd.log reporting "Unable to create SSO facade: Invalid response code: 404 Not Found". The quick way to fix this is to restart the VMware Secure Token Service, as per VMware [KB2061412](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2061412&src=vmw_so_vex_dsimp_889). This can also be seen on the Appliance, where the following 3 commands are required:

	/etc/init.d/vmware-stsd restart  
	/etc/init.d/vmware-sts-idmd restart  
	service vmware-vpxd restart  

Another issue with a Windows Server 2008 based vCenter not starting is where the error 503 Service Temporarily Unavailable is returned and the vpxd log shows that socket connections fail due to time outs. This is caused by a fault in the TCP/IP stack and MS have issued a couple of hotfixes, for Server 2008 and Server 2008 R2. The VMware [KB2033822](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2033822&src=vmw_so_vex_dsimp_889) explains more.   
  
If your Windows Server based SRM service doesn't start on both your protected site and your recovery site, or the service appears to start but is seen to have stopped quite quickly, then an interesting thing to check for is if the service account that is running the service has had a password change. Of course, SRM should not be running as the system account, it should be running under a windows service account.  
  
A clue here is that both the protected and recovery site SRM servers are experiencing the same issue. The account could be locked out of course, but that's easy to check for and remediate! If the password on this account is amended on the server/AD and on the service properties, that is not enough as the SRM installation itself also has to be modified to reflect this password change.   
  
To fix, carry out a modify installation from Windows Programs part of the Control Panel, as per VMware [KB2012112](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2012112&src=vmw_so_vex_dsimp_889). This is an easy task as you're not changing any of the other configs, so your certificates, database ODBC connectivity and database contents etc are retained. I initially found this where the VMware SRM plugin was not found on the C# client on one of my SRM test setups, although I was sure it had been in place previously. Attempting to install the plugin failed, so it was time to hunt down errors in the logs. This investigation quickly led me down a series of issues with the SRM service (where everything was working fine in the past) and it turns out that the password change wrecked everything. Reinstalling the SRM plugin works fine once SRM is modified to reflect the password change.  
  
The vpxd.log file is located on W2K8 at C:\ProgramData\VMware\VMware VirtualCenter\Logs   
On the appliance it is found at  /var/log/vmware/vpx/vpxd.log  
The SRM logs on Windows Server 2008 or 2012 are located at C:\ProgramData\VMware\VMware vCenter Site Recovery Manager\Logs\   
