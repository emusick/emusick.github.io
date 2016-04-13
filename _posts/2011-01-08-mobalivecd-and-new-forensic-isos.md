---
id: 51
title: MobaLiveCD and New Forensic ISOs
date: 2011-01-08T12:17:15+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=51
permalink: /mobalivecd-and-new-forensic-isos/
categories:
  - Forensics
tags:
  - linux
  - virtualization
---
I read about [MobaLiveCD](http://mobalivecd.mobatek.net/en/ "Homepage for MobaLiveCD, a portable ISO launcher") from an [Opexx](http://twitter.com/opexxx "Opexxx's twitter page") twitter post and decided to try it out. MobaLiveCD is a small, portable ISO and bootable USB launcher based on [Qemu](http://wiki.qemu.org/Main_Page "Homepage for Qemu, a virtualization emulator"). It weighs a measly 1.5 MB. Since [DEFT Linux](http://www.deftlinux.net/ "Homepage for DEFT Linux, a computer forensic focused LiveCD") just rolled out version 6, I wanted to give it a whirl along with a few other ISOs I had recently downloaded. Executing MobaLiveCD resulted in an error when trying to copy files to the host system. These files were: _C:\Windows\system32\drivers\kqemu.sys_ and _C:\Windows\inf\kqemu.inf_. Running as administrator is required for these files to copy. After the Qemu instance has been stopped, these files are apparently removed.

After successfully initiating MobaLiveCD, there are options for installing MobaLiveCD file associations for ISOs, running an ISO, and running a bootable USB device. I only tested the ISO option. After choosing to run an ISO, there is an option to use a hard disk. It did not seem to matter which option was selected in except that a file _MobaLiveCD HardDisk.mlc_ (default name and can be changed) needed to be saved when choosing to create a hard disk. Afterwards, the ISO attempts to load. Loading is quite slow. Once it finally loaded, I had some video problems inside the DEFT Linux GUI &#8212; windows would visually disappear and reappear. While MobaLiveCD did work, it did not seem practical unless it is impossible to install a virtualization environment such as [VMware](http://www.vmware.com/ "Homepage for VMware, a virtualization environment") or [Virtualbox](http://www.virtualbox.org/ "Homepage for Virtualbox, a virtualization environment").

After unsuccessfully using MobaLiveCD, I defaulted back to VMware to finish playing with my ISOs. I have not used DEFT Linux much, but at a cursory glance everything seemed to open including the auto-starting of wine for the Windows based programs. It appears as though this was a bugfix and updated package release. For those who do use DEFT more regularly than myself, this should not be much of a departure from previous versions.

Caine also released a new version shortly after DEFT, bumping it to version 2.0. Much like DEFT Linux, this looks like a package update release. A &#8220;gvfsd-metadata&#8221; error greeted me after loading which is never good to see on public releases. The applications seemed to load just fine while running through the menus quickly. Whether one would prefer Caine over DEFT or not will largely be based on preference and not necessarily tool selection. Both are fairly clean and come loaded with the standard tools.

I am waiting for the new release of [REMnux](http://zeltser.com/remnux/ "Homepage for REMnux, a LiveCD for analyzing malware and reverse engineering"). Rumors have it that the new version will be released in the next few weeks. If you have not tried REMnux, it focuses on tools used for malware analysis and reverse engineering. The Enlightenment desktop is implemented which relies on left- and right-click desktop menus. The context menu is fairly bare forcing users to navigate the terminal. Considering the tools, this is to be expected, but it may intimidate some Linux newbies. It is a good idea to read the homepage to get a better idea about REMnux&#8217;s purpose, the provided tools, and some basic navigation tips.

[BlackBuntu](http://www.blackbuntu.com/ "Homepage for BlackBuntu, a penetration testing LiveCD built off Ubuntu") is a new penetration testing LiveCD based on Ubuntu 10.10. However, the current Community Edition version 0.1 did not work for me. [VMware Player](http://www.vmware.com/products/player/ "Homepage for VMware Player, a virtualization emulator") was used (as with all the ISOs in this article) to test. Once BlackBuntu had loaded, the menu bar was not clickable. It does not seem reasonable that this would be an issue with the ISO release itself, but nonetheless, that is what happened. Instead of trying to narrow down the problem, I will wait for the new version which should be arriving 2010-01-24 according to their site news. Unless of course, the urge overwhelms me.

[Peppermint OS](http://peppermintos.com/ "Homepage for Peppermint OS, an Ubuntu based LiveCD utilizing cloud services") caught my attention as it proclaimed to be fast while looking like Ubuntu. It is in fact based off Ubuntu; specifically, the Lubuntu fork. It does load fast and sports the LXDE desktop (hence being based off Lubuntu). What is really interesting though are the included applications, many of which are cloud based. A few they list are: Pixlr, Facebook, Hulu, Last.FM, Pandora, Seesmic Web, YouTube, eBuddy, and some Google applications. It also includes Firefox, Drop-Box, Exaile, Prism, X-Chat, and Transmission. This makes Peppermint a highly web oriented OS that would fit nicely on a netbook. The application selection also gives it a personalized, social feel with many of the main social networking sites featuring their own launchers.

These launchers are really standalone instances of Chromium running using what Peppermint calls &#8220;Ice.&#8221; In their own words:

> Ice is [&#8230;] a Site Specific Browser [SSB] that Peppermint creator Kendall Weaver wrote himself as a means to launch Web Applications and/or Cloud Applications [&#8230;] from the new Peppermint Ice OS. When you launch a web based application using Ice it will call up a custom SSB using the default Chromium Browser. So, essentially, the Ice SSB acts as software that is installed locally but is actually delivered via the Web.

All in all, it is an interesting distribution to play with. I suspect we will see more and more distributions moving towards this style &#8212; fewer installed apps, easier access to desired apps. I was a bit disappointed BlackBuntu did not work for me, but I am looking forward to its new release along with REMnux. Perhaps my hopes for MobaLiveCD were unrealistic, but the idea of being able to launch files with a small, portable application was exciting. Hopefully future releases work out the performance issues and add some clarity around the few buttons that it provides. The above should not deter you from playing around yourself, but merely give you an idea what to expect.

**TL;DR**

MobaLiveCD and BlackBuntu worked less than expected. Cain and DEFT were mainly package updates. Waiting on REMnux to update. Peppermint looks neat.