---
id: 60
title: Betraying the EnCase File Carver
date: 2011-01-18T18:14:16+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=60
permalink: /betraying-the-encase-file-carver/
categories:
  - Forensics
tags:
  - encase
  - ftki
---
After silently venting over a cup of hot chocolate, I had an idea to bypass EnCase&#8217;s knack for unsuccessfully carving unallocated space. The issue arises after a week of attempting to carve files from unallocated. Originally, and against all sanity, I attempted to carve multiple known file types (AVI and JPG) from the case processor. I grew tired of watching my machine die after two days and stopping the process. It was only then that I realized it had worked, temporarily, before network activity halted. This was evidenced by the fact that bookmarks existed that did not exist before. Reassured, I set forth once more narrowing my scope to only JPGs. Four days later, I killed the process after waiting 4.5 hours for my machine to wake up from it&#8217;s slumber (not sure what induces such a heavy sleep).

The solution I have mentally proposed involves exporting the unallocated space out (most likely with FTK Imager to spite EnCase). Once exported, it would be a trivial matter to grep for the desired file headers or use an actual file carver such as Foremost. Manually sorting greps may take longer, but generating an offset list would be exceptionally quick. One could use a hexdump utility to grab the file, or a portion of it, if a known footer exists. Cheating is most likely the best option for quickly previewing the carved results. The rough idea would be to dump a specific amount of data after the target offset. For instance, beginning with offset fubar, read snafu lines into a new file. This will almost guarantee that the proper file will not be preserved, but standard video and image players (ie. VLC and IrfanView of XnView) will work their magic and display the file. After identifying the files sought, one can go back and do a more thorough carve.

The above is not ideal, but when frustrations rise, drastic measures are called for. None of this has been tested, but it works in theory.

**TL;DR**

Instead of using EnCase&#8217;s case processor for file carving, export the unallocated space and run external tools against it.

**Update:**

<div>
  <p>
    Since writing this, I have begun using the <a title="Homepage for SIFT" href="http://computer-forensics.sans.org/community/downloads">SANS Investigative Forensic Toolkit</a> (SIFT). For carving, I use FTK Imager to export all unallocated space. It is easier if export all chunks from a single evidence item into a single directory; this reduces the number of audit reports and repetitious command execution. These chunks are copied to my local host (typically, our evidence resides on an isolated file server) to a folder being shared within VMWare. Launch SIFT through VMWare, navigate to the shared folder, and begin running foremost. Make sure to read the man page (man foremost) to make the best use of foremost and its config file, but a basic execution might look like:
  </p>
  
  <pre>foremost -t avi,wmv,mpg,mov,jpg -i /path/to/unallocated/chunks -o /path/to/UAC_EvidenceItemX</pre>
  
  <p>
    If you are looking to build your own Linux environment instead of using SIFT, I highly recommend <a title="Amazon page for DFwOST" href="http://www.amazon.com/Digital-Forensics-Open-Source-Tools/dp/1597495867">Digital Forensics With Open Source Tools</a> by Cory Altheide and Harlan Carvey.
  </p>
</div>