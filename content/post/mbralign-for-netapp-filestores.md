---
author: Dave Simpson
date: 2013-06-06 15:20:00+00:00
draft: false
title: mbralign for NetApp filestores
type: post
categories:
- Posts
thumbnail: "img/20130606netapp.png"
description: "mbralign for VMware filestores"
tags: [VMware,NetApp]
---

## Intro
Migrating VMs to a NetApp filer is all well and good, but there's a disk alignment issue to get past once those migrations are done, otherwise your expected performance will be seriously impacted.   
  
You should use the version of the mbralign tool included with the latest NetApp Virtual Storage Console (VSC) to check VMDK partition alignment. There is a version of mbralign for ESX hosts and one for ESXi hosts and you're given the option to select the correct one at download. Grab the VSC from [http://support.netapp.com/](http://support.netapp.com/)  

The mbralign tool is effective on both  -flat.vmdk and fixed .vhd files - as long as they are partitioned using an MBR partition table, rather than GPT.

## Scanning
To scan for misaligned vmdk's from an ESX host console, change to the directory where mbralign is installed and enter the following command;

	./mbralign { --scan all | filename }

The --scan all option scans all -flat.vmdk files, whereas entering a -flat.vmdk scans one file. 

The command displays whether the VMDK partition is correctly aligned, you will see information about the file(s) ending with Aligned: No or Aligned: Yes 

## Before you Remediate

Consider this relatively long list of caveats and warnings;  
  

- For ESX clusters, you must run the mbralign program on the ESX host where the VM is currently registered. For NFS datastores, the mbralign program cannot detect if the VM is powered down if the VM is running on another ESX host.   

- Running the mbralign program on a VM that is powered on can corrupt the VMDK. You must then restore the VMDK from the backup created by mbralign.   

- When you use the feature to preserve Windows drive letter mapping, you start with the VM powered on, and mbralign powers it down after collecting drive letter mappings.   

- If you do not want to shut down the VM, take either a Data ONTAP Snapshot copy of the volume containing the Datastore LUN or NFS Datastore, or clone the VM in question, and then run mbrscan against the cloned copy.   

- Be aware that mbralign can take a number of minutes per gigabyte of storage to align files.   

- Consider VMware vCenter Converter as an option to align VMs if you cannot power machines off for long.  
  
## Remediation Steps
  
1 - Remove any VMware snapshots from the VM that is to be realigned. You can also think about removing any other drives that don't require alignment from the individual VM.
2 - For Linux VMs, and Windows VMs with only a C:\ drive, shut down the VM. For a Windows VM with multiple drive letters mapped, the VM must be running so that mbralign can collect the drive letter information before it shuts the VM down. 
3 - On the ESX or ESXi host console, change to the directory containing the .vmdk file for the VM. 
4 - Enter the following command: 

	path/mbralign name.vmdk

path is the path where the mbralign program is installed.   
name is the name of the VMDK file being aligned. 

5 - If prompted, enter yes for a Windows VM to automatically collect and restore drive letters. Enter the Windows Administrator credentials for the VM. The VM is automatically shut down after the drive letter information is collected. 

6 - When prompted Are you sure that no snapshots/linked clones exist for this vmdk? Enter y. 

**Attention:** The use of mbralign on a VMDK file that has a snapshot or linked clone associated with it can result in unrecoverable data loss or data corruption. 

7 - For Windows guest operating systems for which you are not using the drive letter restore feature, restart the VM and verify that the guest operating system boots successfully. 

8 - For Linux guest operating systems using the GRUB boot loader, reinstall GRUB before restarting the VM. 

9 - After verifying the VM has booted and is operating correctly, delete the backup files created by mbralign. These files are saved in the same directory as the .vmdk file and have names ending in -mbralign-backup. 
