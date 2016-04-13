---
id: 70
title: MiTeC Windows Registry Recovery
date: 2011-02-09T18:40:38+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=70
permalink: /mitec-windows-registry-recovery/
categories:
  - Forensics
  - 'Test &amp; Review'
tags:
  - registry
  - windows
---
I was reading [ForensicArtifacts&#8217; RecentDocs article](http://forensicartifacts.com/2011/02/recentdocs/ "RecentDocs article by ForensicArtifacts") and noted the registry viewer application that was used. Everyone talks about [AccessData&#8217;s Registry Viewer](http://accessdata.com/support/adownloads "Resource and download page for AccessData's Registry Viewer"). While it is a really great tool with support for decoding common values and nice highlighting for important keys, it is a commercial product and one that not everyone has. However, [Windows Registry Recovery](http://www.mitec.cz/wrr.html "Homepage for MiTeC's Windows Registry Recovery, a registry browser") by MiTeC is cost free and installation free (a single 727 KB executable that runs from portable media). It allows for loading of multiple hives at once. Each hive is opened in a new sub-window that lists &#8220;explorer tasks&#8221; which are logical groupings of registry entries. Not all explorer tasks are available for every hive (ie. SAM information is not available in a NTUSER.DAT hive) and there appears to be no way to aggregate results from multiple hives (ie. import all suspect hives and access any explorer task). This means that operators will still need to be familiar with what hives hold what data.

There is a &#8220;raw data&#8221; task which allows one to browse the registry in its native structure without logical groupings. When clicking on specific key values, it opens a nice viewer that includes the raw hex, a conversion pane for dates and times, and a summary tab that lists the hash value. One can swap endian-ness and toggle Unicode to make the ASCII more readable. For forensic purposes, some will balk as it does allow one to modify data. However, if you are using this to augment an investigation then there should be no problem.

Windows Registry Recovery allows one to export a report which is a CSV file. However, in testing with version 1.5.1.0, this resulted in an error message &#8220;Abstract Error.&#8221; Exporting to the REGEDIT4 format did work. This allows the exporting of entire root keys or single, selected keys to the standard .reg format. In all, it has a few flaws, but makes for a handy utility to have nearby. It is better than loading hives through Microsoft&#8217;s regedit, but does not have the stability of AccessData&#8217;s Registry Viewer. That said, it has some nice features over Registry Viewer. Looking forward to future updates.

**TL;DR**

Windows Registry Recovery by MiTeC is a nice, portable application for browsing registry hives. It has some flaws, but is still useful.

**Update (February 10, 2011):**

I got in touch with the author of MiTeC and he has already released a fix for the report issue. He said there were also some interface changes to make it more compatible with themes. The version reported under help still says &#8220;1.5.1.0,&#8221; but this fixed version should be 1.5.2. After testing, the CSV report appears to work and generates a tab delimited file. When saving, it is not necessary to provide an extension; however, if you do, it will not double the extension which is quite nice. It&#8217;s great to see such a quick response. Looking forward to using more tools found on [MiTeC](http://www.mitec.cz/index.html "Homepage for MiTeC").