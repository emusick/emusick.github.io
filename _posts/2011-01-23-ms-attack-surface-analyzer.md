---
id: 62
title: MS Attack Surface Analyzer
date: 2011-01-23T13:18:21+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=62
permalink: /ms-attack-surface-analyzer/
categories:
  - Security
  - 'Test &amp; Review'
---
Microsoft recently released a beta version of their [Attack Surface Analyzer](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=1283b765-f57d-4ebb-8f0a-c49c746b44b9 "Download page for Attack Surface Analyzer, analytical and comparison tool"), which compares two system snapshots and reports on the differences. Designed as a security auditing tool, it can also function nicely  for testing malware. It is a static tool unlike [Digital DNA](https://www.hbgary.com/products-services/digital-dna/ "Homepage for Digital DNA, an anomaly detection monitor  ") and others. I downloaded this a few days ago and was kind of waiting for someone else to review it. Although a few have mentioned it, no one seems to have run it yet. So, I broke down. Installation and execution is straight forward. After selecting a new scan and setting a path, the following dialog appears while it scans the machine.

<div style="width: 610px" class="wp-caption alignnone">
  <a title="Attack Surface Analyzer sample report" href="/content/img/MS_ASA.png"><img title="Attack Surface Analyzer report" src="/content/img/MS_ASA.png" alt="Attack Surface Analyzer report" width="600" height="711" /></a>
  
  <p class="wp-caption-text">
    Various test items enumerated
  </p>
</div>

Two main files are created during a scan: the &#8220;data&#8221; directory and a cab file. The data directory contains the XML files generated during the last scan. Each of the enumerated scans shown in the above screenshot are their own XML file; among others. This is then compressed into a cab file. The cab file follows a name convention of &#8220;Hostname\_ASAVersion\_Date\_Time.cab&#8221;. As an example, my file was titled &#8220;RAGE\_5.1.3\_2011-01-23\_17-26-57.cab&#8221;. The time field is GMT and not local time.

Each scan took roughly 10 minutes to complete. The data directory weighs around 134 MB and the cab file is a mere 6.9 MB. The time and sizes of each scan will depend on the a number of factors, but this should be a general idea of what to expect.

Once two scans have been completed (a &#8220;baseline&#8221; and &#8220;product&#8221; scan), a report can be generated that compares the two for differences. The report consists of three files stored in a directory named after the &#8220;product&#8221; scan. The files are the main &#8220;report.html,&#8221; a &#8220;help.html&#8221; which is a glossary of terms, and a &#8220;logo.png.&#8221; This directory is self-contained and can be transported or archived without worrying about potentially breaking links.

I did not pick the most interesting of applications, but I was itching to try out [Quake Live](http://www.quakelive.com/ "Homepage for Quake Live, Quake 3 Arena for your browser") (which, by the way, is extremely fun and works perfectly in both FF4 and Chrome). A few ACL warnings were produced for files and directories that could be tampered with. The most interesting area is the Attack Surface tab, which lists service and network information. If you read [Checking ASLR](http://blog.didierstevens.com/2011/01/18/quickpost-checking-aslr/ "How to check ASLR for services and applications in Windows 7") by Didier Stevens, you will notice the ASLR flags under the service information section. Since it was running out of Chrome, it appears that anything Chrome related was noted with regards to network information. It&#8217;s interesting and much more involved than a utility such as [RegShot](http://sourceforge.net/projects/regshot/ "Homepage for RegShot, a registry snapshot and comparison utility"). For what it&#8217;s worth, here is a [sample report for the Attack Surface](/content/img/MS_ASA.png "Attack Surface Analyzer sample report").

**TL;DR**

Attack Surface Analyzer is an interesting utility that does more than RegShot and has some benefits for malware testing and application validation. It will require some toying with to better understand how it may be useful to you specifically.