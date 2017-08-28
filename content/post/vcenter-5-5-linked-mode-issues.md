---
author: Dave Simpson
date: 2015-10-19 20:37:00+00:00
draft: false
title: vCenter 5.5 Linked Mode issues on Windows Server
type: post
categories:
- Posts
description: "SRM 5.5 Linked Mode problem"
tags: [SRM]
---

I recently saw a problem where a vCenter linked mode configuration appears to have failed half way through. It's highly unusual in that from the C# Client when certain users log in to certain vCenters, they can see the newly added vCenter visible in linked mode as if everything was perfect. Other C# client users, anyone logging in to other vCenters or anyone using the web client does not see this intended end state. The new vCenter does not see any other servers and running the linked mode tool suggests that it is not in linked mode at all.  

When you want to check the GUIDs related to the ADAM databases, which should be replicating around between the vCenters in Linked mode, then you need to look in the ADAM database itself on each vCenter and also correlate that with the contents of the instance.cfg file which should be found in C:\programdata\vmware\vmware virtualcenter\instance.cfg

The instance cfg file looks something like this  
  
    
	#Thu Mar 06 15:44:32 GMT 2014
	applicationDN=dc\=virtualcenter,dc\=vmware,dc\=int  
	instanceUuid=45DE9937-BD12-4264-98AB-10E393F789A2
	ldapPort=389
	ldapInstanceName=VMwareVCMSDS
	ldapStoragePath=C\:ProgramData\VMware\VMware VirtualCenter\VMwareVCMSDS`



The instanceUuid is your vCenter UUID which you can find in the ADAM store.  
  
Run ADSI Edit and connect as shown below;  


[![ADSI Edit 1](/img/20151019adsiedit1.png)](/img/20151019adsiedit1.png)

  
  
You need to enter the Connection Point and Computer fields as shown above. Cut and paste the DN from the instance.cfg file if you like.  
  
Once connected, open up the instances OU and click on one of the UUIDs shown and you should see something like this;  


[![ADSI Edit 2](/img/20151019adsiedit2.png)](/img/20151019adsiedit2.png)

  
You should see CN entries for both VIMAPI and VIMWEBSVC for each of your vCenters operating in linked mode. Match the UUIDs shown here with the instance.cfg file and the vmw-vc-URL entry in the Properties box (as shown above) and you will know that everything ties up correctly. Anything unusual here is indicative of problems. The information in vSphere 5.5 should replicate between ADAM stores, so if you don't have all the UUIDs shown on all your vCenter servers, then some think that there are more vCenters in linked mode than others do, That is clearly not going to work out well for you.  
  
It's also possible that you can have old entries in here of servers you may have disposed of, but traces of them remain. VMware tell me that it is safe to delete the stuff you don't want, but you should back up your ADAM stores first!  To do this, refer to "Manually backing up and restoring the VMware vCenter Server 4.x and 5.x ADAM instance data" [KB1029864](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1029864)  
  
  
That process will show you something like this...  


[![dsbutil](/img/20151019dsdbutil.png)](/img/20151019dsdbutil.png)
  
Good to know!  
  
In the end I fixed this by unlinking the two original vCenter servers on the day I was cutting everything on one site over from the old vCenter to the new one. Then the intended final pair linked up just fine.  
  
  

