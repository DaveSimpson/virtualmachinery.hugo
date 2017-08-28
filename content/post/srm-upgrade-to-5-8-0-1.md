---
author: Dave Simpson
date: 2015-03-26 21:01:00+00:00
draft: false
title: Upgrading Site Recovery Manager 5.5 to 5.8.0.1
type: post
categories:
- Posts
thumbnail: "img/20150326srm.jpg"
description: "VMware vCenter SRM upgrade"
tags: [VMware,SRM]
---

More messing around in my lab and it was time to upgrade SRM from 5.5 to 5.8, including an update of the vCenter itself to 5.5 u2d as well as the IBM SVC SRA as precursors to the SRM upgrade itself.   
  
Upgrading vCenter is pretty simple as long as you run a custom installation and step through the components one at a time, SSO first through to vCenter 4th and last. Upgrading an SRA is also straightforward. I found moving from SRM 5.5 to 5.8.0.1 to be considerably more tricky.  
  
The SRM installation seems easy enough, there's an upgrade option where all you need to do is confirm your password information for the account running the SRM service and the account connecting to vCenter itself (they might even be the same account). All the other settings can be retained, same certificates and everything. Coupled with the fact that SRM 5.8 comes with the web client plugin installed as part of the update, it should only take a few minutes, surely?   
  
Wrong!  
  
  
I ran the updates in parallel on both lab sites, the protected site was all looking good, the SRM icon appeared in the web client without a hitch.  
  
[![SRM Icon now only in the web client](/img/20150326srmup1.png)](/img/20150326srmup1.png)  

The recovery site did not show the icon though, rendering that site half useless at this point. I might be able to recover to it, but I would not be able to do much once there, plus if I lost the protected site, how would I even access the recovery site web plugin?! I was not too perturbed by all this though, since I'd done some [reading around in the VMware vCenter SRM 5.8 Documentation Center](http://pubs.vmware.com/srm-58/index.jsp?topic=%2Fcom.vmware.srm.install_config.doc%2FGUID-55A0D565-333C-4A5D-9B34-429DB48DBF5D.html&src=vmw_so_vex_dsimp_889) beforehand and knew that if you run the modify installation of SRM then you can update the user account settings once more. I had no luck trying this approach though, there was no change in the overall situation at this point. That said, the sites were still showing up as being paired, my old tried and tested SRM 5.5 protection groups, recovery plans etc. were also in all place, so on the surface, things didn't look so bad, as the "Guide to configuring SRM" view that appears on a lot of pages in the web client shows....  

[![Guide to configuring SRM](/img/20150326srmup3.png)](/img/20150326srmup3.png)  

Even the history and SRM reports were still available from the times I'd failed over and failed back under version 5.5. Whilst focusing on the missing icon, I had not noticed at this point that there were other issues evident, which I will come on to later.  
  
Now at this point, curiosity got the better of me, would a recovery actually work with a dodgy recovery site? There were clearly issues with the new platform but this is the sort of test you don't get the chance to carry out very often, so I punched the recover button and left things running for a bit.   

Don't do this if you're not messing around in your lab! 
  
Not wise to mess with something that is clearly not right, but luckily for me, all my protected VMs ended up running in the recovery site, but as the law of sod would dictate, something else happened in my lab, resulting in a lack of operable hosts in the protected site during the recovery as a result of a disk failure and other oddness. This meant that the VMs in the protected site were not shut down first, nor were the protected site datastores unmapped from hosts. The freshly mapped datastores in the recovery site had not been renamed to remove the "snap-" start to their names either. This was a clue for another problem, as I no longer had any of the custom settings that I modified my SRM 5.5 installation with carried over at either SRM 5.8 site. All of those settings had to be reset in the web client. (this is much easier than in the previous version). None of this would be a massive deal for most real DR situations as the really important thing is recovering to the recovery site quickly to keep the business alive. In my particular case, the lab test VMs are not on the network anyway, so most of this was no trouble at all. The key point here is that the protected VMs were all up and running in the protected site really quickly, faster than previous versions of SRM. So, not so bad perhaps?  
  
So now I knew that SRM 5.8.0.1 worked under sub-optimal conditions, I had to try to fix everything to start working on a proper setup. I tried another modify installation, a repair installation, a remove and reinstall installation on the recovery site, all whilst changing as little information as possible, but nothing was fixing that AWOL SRM icon issue. Clearly this was more than an account problem.  
  
Having no icon in vCenter in the protected site (the one now running the VMs) was not the only issue as SRM also showed errors in trying  to establish communication with the SRA, with an inability to log in. More trouble was clear as I looked around more, since although the Client Connection status all reported OK, the SRM Connection was not happy.  

[![SRM Connection error](/img/20150326srmup2.png)](/img/20150326srmup2.png)  
 
Normally you get this sort of error if the SRM service is not started, but mine was definitely started and I'd re-typed the service account credentials plenty of times too during all those modify installs!  
  
I could also see lots of errors in the SRM logs on both sites (generally found at C:\ProgramData\VMware\VMware vCenter Site Recovery Manager\Logs) along the lines of  

	2015-03-25T13:59:00.865Z [12556 warning 'RemoteVC' connID=vc-admin-ff91] Failed to connect: (vim.fault.InvalidClientCertificate) {  
	-->    dynamicType = ,   
	-->    faultCause = (vmodl.MethodFault) null,   
	-->    msg = "Received SOAP response fault from []: loginExtensionBySubjectName  
	--> Cannot complete client certificate validation.",   
	--> }  
  
"InvalidClientCertificate" and "Cannot complete client certificate validation" clearly aren't good.  
  
Continuing to take things one step at a time, I figured that if there's communication errors, what about doing modify installs at both sites and updating the user account information? That seemed to do the trick. Suddenly I had the SRM icon visible in both sites. I still had that SRM Connection status problem though. This issue did not get resolved until I did a repair installation on both sites that replaced the certificates with new ones  - even though the installation claimed that the existing certs were valid as below.  

[![Certificate validity](/img/20150326srmup4.png)](/img/20150326srmup4.png)  

Generally, you should pick the highlighted option to auto generate a new cert rather than the defaulted option to use the existing certificate. Once this modify installation completed I then followed up by pairing the sites once more, to force the new certificates to be used.  

[![Pair Sites](/img/20150326srmup5.png)](/img/20150326srmup5.png)  

The pair site option is not always available (if your sites are paired properly, for instance!)  

Because I have yet to replace my disk mappings in the original protected site or simply create a new recovery plan instead, then I don't yet know if I am going to fall victim to the ["linked mode" problem](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2093902&src=vmw_so_vex_dsimp_889) that stops SRM from carrying out a recovery until linked mode is removed. Fortunately that's a simple fix.  

  1. On the recovery site vCenter Server, navigate to Start > All Programs > vCenter Server Linked Mode Configuration. 
  2. Click Next, select Modify Linked Mode configuration and then click Next. 
  3. Ensure that the checkbox Isolate this vCenter Server instance from Linked Mode group is selected and then click Next. 
  4. Click Continue to isolate the vCenter Server. 
  5. When the wizard is complete, check that the Site Recovery Manager service is still running and start it if necessary. 
  6. Log out of the vSphere Web Client and again log in. You should now see the Array Managers, Protection Groups and Recovery Plans and should be able to run the Recovery. 
  
To summarise so far from issues I faced after the 5.8 update;   

  * Record any Advanced Settings changes for posterity before you start the SRM upgrade
  * Check the log files on both sites for errors after the upgrade
  * Carry out modify installations on both sites (reaffirming passwords) if the SRM icon doesn't show up
  * Carry out any modify installations (replacing certificates) on both sites if there are certificate validation issues seen in the log files
    * Re-pair the sites using the new certificates if you issue them
    * Re-establish communication with the SRAs once new certs are in place
  * Check that any custom Advanced Settings have been retained
 
 
Oh, by the way, if you want to know about setting up SRM 5.8 from scratch, then there's a [post from Cody Hosterman ](http://codyhosterman.com/2014/09/11/vmware-vcenter-site-recovery-manager-5-8/)which tells you all about that and discusses some of the new features in 5.8 as well. Check it out!
