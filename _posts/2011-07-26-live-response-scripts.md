---
id: 96
title: Live Response Scripts
date: 2011-07-26T10:20:29+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=96
permalink: /live-response-scripts/
categories:
  - Forensics
  - Programming
tags:
  - incident response
  - linux
  - mac
  - scripts
  - windows
---
2016-04-12 Update: Removed links to scripts. They will be added to a repo.

Creating a live response script has always been an interest of mine. After reading [Real Digital Forensics](http://www.amazon.com/Real-Digital-Forensics-Computer-Security/dp/0321240693 "Amazon link for the Real Digital Forensics book"), I added some tools and changed my format some. It wasn&#8217;t until I recently attended the Federal Law Enforcement Center&#8217;s (FLETC) Computer Network Investigations Training Program (CNITP) that I had a real use for any type of script. During the two week class, I pulled out my old scripts and added some updates. They include most all of the commands covered in the class as well as some new ones (**net share** instead of their suggested **net view localhost /all**). I added a bunch of new comments, listed the executables the script expects to find for the Windows version, and began converting the Linux version to a Mac version. CNITP was my first real exposure to a Mac so it is missing good information and could stand some work.

All of the files are commented; although, the comments could be more verbose at times. The Windows Information Extractor (wie.bat) depends on a number of third-party tools; mostly from [Sysinternals](http://technet.microsoft.com/en-us/sysinternals "Microsoft homepage for Sysinternals"). The Sysinternals tools are: autoruns, psfile, psgetsid, psinfo, pslist, psloggedon, and psservice. The other utilities are [find](http://unxutils.sourceforge.net/ "UnxUtils homepage for the suite containing find"), [Fport](http://www.mcafee.com/us/downloads/free-tools/fport.aspx "McAfee homepage for Fport"), and [PwDump7](http://www.tarasco.org/security/pwdump_7/ "Tarasco Security homepage for PwDump7"). The Linux Information Extractor (lie.sh) and Mac Information Extractor (mie.sh) do not rely on third-party tools.

Feel free to use the scripts how you would like. You must get the third-party Windows tools separately. If you do use the scripts or have any suggestions, please comment and let know. It&#8217;s always a learning experience.

Linux Information Extractor: lie.sh

Mac Information Extractor: mie.sh

Windows Information Extractor: wie.bat
