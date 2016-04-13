---
id: 74
title: Spring Cleaning
date: 2011-02-20T11:09:23+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=74
permalink: /spring-cleaning/
categories:
  - Security
tags:
  - howto
---
Over time, systems begin to grow cruft. User data long forgotten lies in varying states of decay. It seems that regardless of how proactive one is in defending their free space, rot creeps in and needs to be disposed of. Depending on needs, the clean up process can vary. Outlined below are three different categories that set out some basics to cover. Personally, I tend to keep up with the Advanced section along the way and have most of my MS Windows [services disabled](http://www.blackviper.com/ "Homepage for BlackViper which details which services can be safely disabled"). The Paranoid section is one of those once-a-year scenarios while the Beginner section is usually done when needed (roughly, once a quarter for my usage). Find what works best for you.

In the Beginner tier, we have the basic options with minimal configuration changes. These are the steps you will want to take any time the system is feeling sluggish or you need to reclaim some disk space.

  1. [Disable hibernate](http://www.sevenforums.com/tutorials/819-hibernate-enable-disable.html "An article describing how to disable hibernate in Windows") (**powercfg -h off**)
  2. Uninstall unneeded applications
  3. Delete unneeded files
  4. Run [CCleaner](http://www.piriform.com/ccleaner "Homepage for CCleaner, a system clean up utility")  &#8220;Cleaner&#8221; tab (after closing all browsers)
  5. Run CCleaner &#8220;Registry&#8221; tab
  6. Run [Defraggler](http://www.piriform.com/defraggler "Homepage for Defraggler, a disk defragmentation tool")

Note: Both CCleaner and Defraggler can be downloaded as portable applications. This means that they will not add cruft to the system if this is the only time you plan on using them. At the bottom of the download pages, there is a section called &#8220;Builds.&#8221; Click the &#8220;builds page&#8221; link and select the &#8220;Portable&#8221; version (zip file, no installer).

Once Defraggler completes, it is time to re-enable any required services that you previously disabled. In this case, hibernate (**powercfg -h on**).

The Advanced tier adds some additional items that are more security related. After disabling hibernate, disable [System Restores](http://support.microsoft.com/kb/310405 "Microsoft Knowledge Base article describing how to disable System Restore") and [Volume Shadow Copies](http://social.answers.microsoft.com/Forums/en-US/w7performance/thread/1d6c21d0-744a-4a64-8bf8-36dff4c1c981 "Microsoft Social Answers thread on disabling Volume Shadow Copy"). This will speed up installations, but will delete any saved data for these services. If you are using these as a backup solution, then you will have to decide the risk. The next step is to perform any MS Windows updates and update all required, installed applications.

Proceed through the Beginner steps, clearing all the junk off with CCleaner. Before running Defraggler, we are going to wipe all unused space. You might be wondering why this is not in the paranoid section, but wiping can kill off other objects which we typically do not have access to such as the Recycle Bin, Swap, and MFT records. These are a bit technical, but the idea is to purge unused data and wiping can accomplish that. [BCWipe](http://www.jetico.com/wiping-bcwipe/ "Homepage for BCWipe, a file and disk wiping application") is a great little utility to use. It is commercial, trial demonstration for scheduled tasks, and must be installed; however, it is quite nice even with the nag windows. There are ways to accomplish the same tasks without using the trial features.

The Paranoid tier is more of an auditing phase. Prior to starting CCleaner, [audit passwords](http://erikmusick.com/journal/2010/12/30/password-management.html "Nekyia article on password management"), delete old accounts no longer in use, and migrate questionable or personal data into encrypted volumes. How one goes about these tasks is largely up to the user. Some suggested tools to look at are [KeePass](http://keepass.info/ "Homepage for KeePass, a password management tool") and [TrueCrypt](http://www.truecrypt.org/ "Homepage for TrueCrypt, an application for creating encrypted volumes"). If you are using [GPG](http://www.gnupg.org/ "Homepage for GPG, a public key encryption suite") or other encryption schemes, generate new passwords and revoke any temporary accounts (make sure you do not have data still encrypted using keys you want to revoke!). KeePass has a portable version and [TrueCrypt can become portable](http://www.truecrypt.org/docs/?s=truecrypt-portable "How to make TrueCrypt a portable application") after installation (install, copy the application to a portable device, and uninstall the original).

While the above is not comprehensive, it should provide a solid base for cleaning a system. Security and performance tweaks were not described, but can be implemented alongside the cleaning process. The fewer services that are running, the slower future build-ups will occur. Enjoy a more responsive system.

**TL;DR**

Like food in the fridge, over time data &#8220;evolves&#8221; into something undesired. Stop backup services, delete and uninstall unnecessary stuff, clean temporary files (ie. CCleaner), defragment (ie. Defraggler), wipe free space, and re-enable any required services. Find a Martin Scorsese (or three) because the process will take a while.