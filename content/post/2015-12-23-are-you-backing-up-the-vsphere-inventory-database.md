---
author: Dave Simpson
date: 2015-12-23 18:10:00+00:00
draft: false
title: Are you backing up the vSphere Inventory Database?
type: post
url: /2015/12/23/are-you-backing-up-the-vsphere-inventory-database/
categories:
- Posts
description: "Why you should be backing up the vSphere Inventory database, but might not be"
tags: [vCenter,VMware]
---

The Inventory service came about as a separate item in vSphere 5.x and is the place where all of your web client tags get stored (you ARE using tags, right?) but it also gets used to cache queries destined for the vCenter database from the web client, which reduces the load on the vCenter server database. It's also a database that grows substantially if you ever recover a load of VMs with SRM or similar, but that's another story.  
  
The upshot of all this is that there's data in here that does not exist anywhere else and that means that you should be able to backup and restore that data as required.  
  
I was rebuilding a vCenter server recently, which got me thinking about this task as I ran down my post-install checklist. It's one of those hidden tasks that doesn't quite get the attention that it deserves, especially since it is so easy to do, as we will discover here...   
  
On the old Windows Server side of things, you simply need to invoke a batch file and pass it the name of your desired backup file. Restoring is equally as simple.  
  
From a command prompt, cd to C:\Program Files\Infrastructure\Inventory Service\scripts or wherever you installed vCenter and then run the command  

    backup.bat -file _backup_file_name_  
  
To restore, stop the vCenter Inventory Service and then from the same location, run the command  
    
    restore.bat -backup _backup_file_name_  
  
If you are using a Linux based vCenter, then same basic process needs following. From a console you will need to navigate to /usr/lib/vmware-vpx/inventoryservice/scripts/ and run commands  

    ./backup.sh -file _backup_file_name_  

    ./restore.sh -backup _backup_file_name_


Again, you'll need to stop the Inventory service before a restore;  

    service vmware-inventoryservice stop
  
Once you have done a backup and seen the "Backup Completed Successfully" message a couple of times, then of course you'll want to schedule this. The Windows Server scheduler will do a job for you, but you can go to town on your automation and reporting here, do whatever you want!  
  
For a more complete description of each of these topics, you can refer to the content in the [vSphere 5 Documentation Center](https://pubs.vmware.com/vsphere-50/index.jsp?topic=%2Fcom.vmware.vsphere.install.doc_50%2FGUID-518228D1-E305-457C-B552-50DAB4BDF6B1.html).  
  
And just to mention it at the end, a backup is only worth taking if you have proof that someone else can restore it.
