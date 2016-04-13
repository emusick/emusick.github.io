---
id: 111
title: FileZilla Password Caching
date: 2011-10-08T15:26:55+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=111
permalink: /filezilla-password-caching/
categories:
  - Forensics
  - HowTo
  - Security
tags:
  - ftp
---
Note, this article was written a while back and the position of the FileZilla developers may have changed. The information presented should still be relevant.

There were a [number of emails](http://seclists.org/fulldisclosure/2010/Oct/114 "SecList thread for "FileZilla's silent caching of user's credentials"") floating around regarding the security of Filezilla. Specifically, it stores login information in plain-text on the host system. This information is stored in _C:\Users\<user_name>\AppData\Roaming\FileZilla\sitemanager.xml_ (or similar paths for different platforms). The implication of this is that passwords are easily available in the case of stolen (or misplaced) laptops or by malware targeting this information. Using FileZilla on insecure, public machines may also result in this information being stored, visibly, on machines outside of your control. Forensically, it means an easy harvest of used passwords for cracking applications.

There is a [configuration file](http://forum.filezilla-project.org/viewtopic.php?f=1&t=10376 "FileZilla Forums, Filezilla Password File") present that can be modified to force FileZilla into a &#8220;kiosk&#8221; mode which prevents this information from being stored. Read the documentation found in the **fzdefaults.xml.example** file and apply the appropriate settings to a new or modified **fzdefaults.xml** file.

The developers of FileZilla have thus far been extremely stubborn and unwilling to change the default way FileZilla handles the storing of passwords. As such, do not expect a change in the near future. This does not mean FileZilla is no longer a viable option for FTP, but it does mean you should be aware of what is being stored. It is also good information for individuals involved in forensic investigations as harvesting these passwords is trivial.

According to the example config, 0 is disabled, 1 prevents passwords from being saved, and 2 prevents writing to config files. These are not cumulative options meaning that if you select 2, your passwords will be saved. So, the following is what you will want to add to your <Settings> section of **fzdefaults.xml**:

<pre>&lt;Settings&gt;
   &lt;Setting name="Kiosk mode"&gt;1/Setting&gt;
&lt;/Settings&gt;</pre>