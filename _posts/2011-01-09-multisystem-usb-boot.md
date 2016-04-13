---
id: 53
title: MultiSystem USB Boot
date: 2011-01-09T21:12:58+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=53
permalink: /multisystem-usb-boot/
categories:
  - 'Test &amp; Review'
tags:
  - linux
  - virtualization
---
There are a few different options floating around when trying to get a single USB device capable of booting multiple ISO images. I ran across <a title="Homepage for MultiSystem, a multiple=">MultiSystem LiveUSB</a> the other day and decided to give it a try. This process started out by reading [How To Boot 10 Different Live CDs From 1 USB Flash Drive](http://www.howtogeek.com/howto/39747/how-to-boot-10-different-live-cds-from-1-usb-flash-drive/ "How To Geek article on MultiSystem"), but it quickly became apparent that some changes needed to occur for my Backtrack 4 on VMware environment. These changes should be standard across all Ubuntu distributions. Before proceeding through all of this, keep in mind that I was not successful in getting [DEFT](http://www.deftlinux.net/ "Homepage for DEFT, a forensic LiveCD") or [SystemRescueCD](http://www.sysresccd.org/Main_Page "Homepage for SystemRescueCD, a system recovery LiveCD") to boot. DEFT is not on the [compatibility page](http://liveusb.info/dotclear/index.php?category/OS-Supportes "Distribution compatibility page for MultSystem"), but SRCD is. Other ISOs or configurations may work, but I was left unsatisfied and stopped debugging. [MultiSystem was recommended by Pendrive Linux](http://www.pendrivelinux.com/multiboot-create-a-multiboot-usb-from-linux/ "Pendrive Linux article on using MultiSystem under Ubuntu"). I have not seen any other article describing the issues I have had so I can only assume that it was my setup. I am posting this in case those complaints were silent and, possibly, as a warning against using BackTrack 4 or VMware. What follows was my adventure&#8230;

After installing MultiSystem following the How-To-Geek article, make sure to read the message that is printed after the installation of Grub2. This part hosed my grub config requiring some manual edits during the grub console in order to boot. I created a new user account after staring blankly at &#8220;_Erreur: pas en root_&#8221; (&#8220;_Do not run as root_&#8220;). I ran \`**adduser my\_new\_user**\` to overcome this problem. Subsequent errors regarding sudo were combatted by \`**adduser my\_new\_user admin**\`. I then added a new entry in _/etc/fstab_ for the USB device as &#8220;_/dev/sdb1    /media/usb     auto    rw,user,noauto    0    0_&#8221; and then created the directory via \`**mkdir -p /media/usb**\`. MultiSystem looks for this directory so other locations may not work (I say &#8220;may&#8221; because _/mnt_ did work partially as I was crawling through different changes).

After an initial failture to boot, I downloaded [Plop](http://www.plop.at/en/bootmngrusblog.html "Homepage for Plop, a boot manager") ([direct download link](http://download.plop.at/files/bootmngr/plpbt-5.0.11.zip "direct download link")) and placed the zip in _/tmp_. From the MultiSystem toolbar, select &#8220;Non-Free,&#8221; &#8220;Installing non-free part,&#8221; and click &#8220;Download PLoP Boot Manager&#8221; to install it. Select close once unzipping is complete, select &#8220;Boot&#8221; from the toolbar, and click &#8220;Boot from Grub/Grub2.&#8221;

After all of this preparation, I logged out and back in as the new user (I could not get **su** or **sudo** to corporate). Since invisible errors were occurring, I executed _/usr/local/bin/multisystem_ from the terminal to answer some permission errors and began adding ISOs. After trying out my new hot rod device, I discovered failure. Hopefully my failure is an isolated experience and others succeed without the above changes. Once I finish some other projects, I will attempt this again using a vanilla Ubuntu VMware install and see if that proves more effective.