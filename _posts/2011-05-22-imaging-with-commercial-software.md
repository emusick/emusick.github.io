---
id: 90
title: Imaging with Commercial Software
date: 2011-05-22T10:54:55+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=90
permalink: /imaging-with-commercial-software/
categories:
  - Forensics
tags:
  - encase
  - ftk
  - guymager
  - imaging
---
I have been a bit busy lately and have not finished the serious of articles to followup Dropbox, but I did run across some interesting information recently regarding imaging and most commercial software. It seems the forensic community enjoys arguing over the correct terminology for &#8220;imaging,&#8221; so use which ever definition you are most comfortable with. In having this conversation on mailing lists, you will also see a few technical observations about sectors that aren&#8217;t read (ie. checksums), can&#8217;t be read, etc. These two issues, terminology and technical specifications, may be fun to argue and highlight some errors in describing our processes. However, I was taken back by the following.

It seems that a lot of software will chunk data into blocks; around 60 sectors seems common. If any error occurs during the reading of that chunk, all following sectors are skipped and the next block of 60 begins. At a worst case scenario, if the first block of 60 clusters errors, all 60 are skipped and the next block is read. This causes two significant problems. One goes back to the above, a misunderstanding of processes. The second may be more critical in that every cluster in the skipped block may not be bad. This means that good, readable clusters may be skipped.

Why is this chunking and skipping done? It seems that vendors were worried about how long imaging might take if numerous errors were found. Instead of waiting out the process, they decided to skip. Some vendors, such as Guidance Software (maker of EnCase) allow you to modify what they call &#8220;Error Granularity.&#8221; According to the [Official EnCE book](http://www.amazon.com/EnCase-Computer-Forensics-DVD-Certified/dp/0470181451 "Amazon link to The Official EnCE: EnCase Certified Examiner Study Guide"), the granularity can be set to 64, 32, 16, 8, 4, 2, and 1. AccessData may offer similar settings, but I am not aware of them (I have had little to no vendor-specific training in either product).

Other imaging packages allow what is referred to as &#8220;reading backwards.&#8221; Clusters are still chunked, but when an error occurs reading picks up from the end of the &#8220;bad&#8221; block and attempts to read backwards. The hope is, if only a single cluster is bad in the block then reading backwards will eventually error out on that cluster. For example, if the first cluster of a 60 cluster block is bad reading will jump to cluster 60 and proceed back to cluster 1. If another error is found during that backwards read, reading will jump to cluster 61 of a second block.

A side issue that came up during the conversation was of zero padding. That is, when clusters are skipped, is the image padded with zeros to maintain the expected file size or is it not padded resulting in an image file (possibly significantly) smaller than expected. When testing your software and writing reports, this is something else to consider.

Interesting information and something I personally did not know. In questioning this on a mailing list, I was kindly corrected (Thank you Voncken).

**TL;DR**

Test your tools. Never trust a vendor. Rely on open source, not bank accounts.