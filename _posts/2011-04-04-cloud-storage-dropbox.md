---
id: 88
title: 'Cloud Storage &#8211; Dropbox'
date: 2011-04-04T20:18:17+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=88
permalink: /cloud-storage-dropbox/
categories:
  - Forensics
tags:
  - artifacts
  - cloud
---
&#8220;Just the facts, ma&#8217;am.&#8221; In an effort to ascertain different artifacts for various cloud storage services, the following procedures were used. A clean, unpatched Windows 7 x64, install was used with [VMware Player](http://www.vmware.com/products/player/ "Homepage for VMware Player, a virtual machine platform") (version 3.1). An initial registry snapshot was taken with [RegShot](http://sourceforge.net/projects/regshot/ "Homepage for RegShot, a registry snapshot and comparison utility") (version 1.8.2) prior to installing the cloud storage application to provide a baseline. RegShot comparisons were performed after the application was installed, after it was initially run, and after an account was created. A file was then uploaded via the application and another regshot taken. Each recorded regshot was coupled with a list of files written to by utilizing [Process Monitor](http://technet.microsoft.com/en-us/sysinternals/bb896653 "Homepage for Process Explorer, a process and registry monitoring utility") (version 2.94). Below are the results.

**Post Installation**

Looking for obvious signs of registry writes, 13 keys were added during the install process. They include keys containing &#8220;Dropbox&#8221; and &#8220;DropboxExt&#8221;. Most values are related to Microsoft&#8217;s &#8220;[tracing](http://technet.microsoft.com/en-us/library/cc957864.aspx "Microsoft TechNet article describing tracing"),&#8221; uninstall information, and ContextMenuHandlers; however, FirewallRules are also added. See PostInstall.txt for the full registry compare.

Files written to include a number of temp files which appear to be removed after installation. Dropbox was installed into AppData\Roaming\Dropbox instead of %PROGRAMFILES%. Start Menu and Prefetch items were created. See db_install.CSV for the full file write log.

**Post Initial Execution**

After installation, Dropbox executed desiring to be configured. As such, there is no differentiation between installation and first launch.

**Post Account Creation**

No obvious signs of registry modification occurred. See AccountCreation.txt for the full registry compare.

A number of databases are written to /AppData/Roaming/Dropbox along with *.db-journal counterparts. Desktop and Link files are created. Files are written to ~/Dropbox/.dropbox.cache. The Dropbox directory is a redirect pointing to the location listed within the Link file. The cache files appear to be removed after use. See db_account.CSV for the full file write log.

**Post File Upload**

No obvious signs of registry modification occurred. See UploadFile.txt for the full registry compare.

The three database files and their *-journal counterparts are updated. No new files appear to be written to. See db_upload.CSV for the full file write log.

**Databases**

During the above steps, five files were created: config.db, filecache.db, host.db, sigstore.db, and unlink.db. These files are SQLite databases with the exception of host.db and unlink.db. The *-journal counterparts are only present during sync&#8217;ing; presumably to roll back in the event of an incomplete transfer.

The config.db has been explained very well by Derek Newton&#8217;s article [Dropbox Authentication: Insecure by Design](http://dereknewton.com/2011/04/dropbox-authentication-static-host-ids/ "Article regarding the insecurity of dropbox authentication via host_id"), but contains a few, self-explanatory keys such as host\_id, dropbox\_path, email, and stats_build.

The filecache.db contains a list of all sync&#8217;d files along with their server path, local filename, size, modified and created time under the &#8220;file\_journal&#8221; table. The file times are stored as Unix Numerical Values and appear to be the original values for the files. On secondary hosts where Dropbox is newly installed, the create time for the directories will be the current time and not the original created time. Other fields exist, but were unpopulated in testing. The table &#8220;mount\_table&#8221; lists directories which are shared with other Dropbox users. Other tables exist, but are not discussed.

Host.db is not actually a database. It contains two lines. The first is a 40 character alphanumeric string fitting the structure of a SHA-1 value. None of the values found in config.db hash to this value. The second is a Base64 string that, when decoded, is the dropbox_path found in config.db (where the root Dropbox folder resides on the host system).

Sigstore.db contains &#8220;hash&#8221; values correlating to the &#8220;local\_blocklist&#8221; values in table &#8220;file\_journal&#8221; of the filecache.db database and sizes. The hash value is not any hash recorded by [HashCalc](http://www.slavasoft.com/hashcalc/index.htm "Homepage for HashCalc, a hash calculation tool") of any file in the dropbox_path directories. It is also not MD5 or SHA-1 encoded as Base32 or Base64.

Unlink.db is a binary file and not a database.

**References**

All aforementioned log files are contained in a single 7zip archive: [artifacts_dropbox.7z](/content/docs/artifacts_dropbox.7z "7zip archive for raw capture logs regarding Dropbox artifacts"). Full captures are included in case there is something significant beyond what was mentioned above.

[Dropbox Forensics Followup](http://forensicaliente.blogspot.com/2011/07/dropbox-forensics-follow-up.html "Forensicaliente's Dropbox Forensics Followup"), by Forensicaliente

[Dropbox authentication: insecure by design](http://dereknewton.com/2011/04/dropbox-authentication-static-host-ids/ "Derek Newton's Dropbox Insecure Design article"), by Derek Newton

**TL;DR**

There is no shortcut, grasshopper. You have to read this one.

**2012-10-01 Edit**

Due to the popularity of this page, I am adding additional resources that may be useful.

<div>
  <div>
    <a href="http://dereknewton.com/2011/04/forensic-artifacts-dropbox/" shape="rect" target="_blank">http://dereknewton.com/2011/04/forensic-artifacts-dropbox/</a>
  </div>
  
  <div>
    <a href="http://forensicartifacts.com/2011/07/dropbox-config-files-windows/" shape="rect" target="_blank">http://forensicartifacts.com/2011/07/dropbox-config-files-windows/</a>
  </div>
  
  <div>
    <a href="http://computer-forensics.sans.org/blog/2011/06/17/digital-forensics-rain-drop-keeps-falling-on-my-box" shape="rect" target="_blank">http://computer-forensics.sans.org/blog/2011/06/17/digital-forensics-rain-drop-keeps-falling-on-my-box</a>
  </div>
  
  <div>
    <a href="http://www.forensicfocus.com/dropbox-forensics" shape="rect" target="_blank">http://www.forensicfocus.com/dropbox-forensics</a>
  </div>
</div>