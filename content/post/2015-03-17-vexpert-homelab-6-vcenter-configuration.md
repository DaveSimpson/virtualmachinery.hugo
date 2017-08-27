---
author: Dave Simpson
date: 2015-03-17 00:13:00+00:00
draft: false
title: vExpert Homelab 6 - vCenter Configuration
type: post
url: /2015/03/17/vexpert-homelab-6-vcenter-configuration/
categories:
- Posts
- Homelab
thumbnail: "img/20150211vsphere60.png"
description: "Configuring a newly built vCenter to work properly"
tags: [Homelab,vExpert,vCenter,VMware]
---

So, you've got a nice new vCenter 6 up and running, maybe you have an external PSC as well? Jolly good! Now what?  
  
There's a whole bunch of additional configuration items that you should look at amending before too long. Log in as your SSO Admin account - administrator@vsphere.local (or whatever you changed it to during the installation) and away we go.  
  
Let's start with something new - the Download Remote Console option. Definitely useful if you want to use console access to any of the VMs in your environment. Pick any VM and below the small remote console window is the Download Remote Console option.   


[![](https://virtualmachinery.files.wordpress.com/2015/03/308f0-hl605.png?w=295)](https://virtualmachinery.files.wordpress.com/2015/03/308f0-hl605.png)

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
Click the Download link to be taken to a VMware webpage where you can select the download and installation options you want. Currently this is fine as long as you are running Windows.   
  
The next of the configuration steps is an oldie-but-goodie from the past. Make sure that your SSO admin account does not time out after 90 days. To do this, head into the Navigator down the left hand side of your vCenter click on the Administration item (not the section in the main pane to the right) and then carry on into Single Sign-On and then Configuration;  
  


[![](https://virtualmachinery.files.wordpress.com/2015/03/0df80-hl601.png?w=300)](https://virtualmachinery.files.wordpress.com/2015/03/0df80-hl601.png)

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
Clicking the Edit button to the top right lets you amend these settings. Lockout Policy and Token Policy can also be amended here. I'm not going to go in to great detail on this since [Vladan's ](http://www.vladan.fr/vcenter-server-6-0-sso-policies/)already done that for you.   
  
  
Whilst you are here under Administration, there's more to do. Under the Deployment item, click into System Configuration. Here's where you find the configuration options for your PSC/vCenter - such as the external identity sources that you will want to set up with your PSC (not the vCenter itself any more, remember). Click on a PSC server that you see in the list and you'll end up in the menus shown below. You're looking for the Active Directory option more than likely.   
  


[![](https://virtualmachinery.files.wordpress.com/2015/03/81f33-hl602.png?w=300)](https://virtualmachinery.files.wordpress.com/2015/03/81f33-hl602.png)

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
Click the Join button to the top right and fill out the details in the Join AD box.    
  


[![](https://virtualmachinery.files.wordpress.com/2015/03/4447a-hl603.png?w=300)](https://virtualmachinery.files.wordpress.com/2015/03/4447a-hl603.png)

  
  
  
  
  
  
  
  
  
  
  
  
  
  
Note that the OU box entry is optional (you can leave it blank) and the User name box MUST be filled out using User Principal Name (UPN) format (user@domain), NOT domain\user format! You will have to restart your PSC afterwards - manually - for this change to take effect. Fortunately for this, all you need to do is step back one step in the navigator to System Configuration and you can select your PSC and restart it at the click of an icon.   
  


[![](https://virtualmachinery.files.wordpress.com/2015/03/8760d-hl604.png?w=300)](https://virtualmachinery.files.wordpress.com/2015/03/8760d-hl604.png)

  
  
  
  
  
  
  
  
  
  
  
  
  
Add the reason for your restart, heed the warnings about not being able to deal with certificates and SSO etc. and away you go. After this, both my PSC and vCenter servers appeared in the Computers OU of my AD.   
  
Now, this is not so much good for vCenter access unless you add the identity source, so back into Administration - Single Sign-On - Configuration and select the Identity Sources tab. Click the Plus icon to add an Identity Source.   
  
[![](https://virtualmachinery.files.wordpress.com/2015/03/e1017-hl606.png?w=300)](https://virtualmachinery.files.wordpress.com/2015/03/e1017-hl606.png)  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
Here it's simply a case of selecting the AD Integrated Authentication Option and selecting Use Machine Account before clicking OK. Pretty simple. This will add another item to your list of Identity Sources.   
  
Next, go set up some permissions for your AD users before you log out. Administration - Single Sign-on - Users and Groups. From the groups tab you can see your vCenter roles at the top, as in the diagram below.   
  


[![](https://virtualmachinery.files.wordpress.com/2015/03/70e59-hl607.png?w=300)](https://virtualmachinery.files.wordpress.com/2015/03/70e59-hl607.png)

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
I have decided to add Windows domain users into the vCenter administrators group by clicking on the Add Group Members button (the button next to where it says System Configuration  
down the left hand side. That brings up the window shown to the right, I've already selected my domain and I'm able to search through the regular users and groups which you would expect to see in AD.   
  
Once you are happy with this setup, you can log out of vCenter. Before you log in again, click the Download Client Integration Plugin option from the logon page.   
  
  
I'll add more to this as I go along...
