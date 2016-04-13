---
id: 122
title: Reducing Directory to Unique Files
date: 2011-10-13T18:28:33+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=122
permalink: /reducing-directory-to-unique-files/
categories:
  - Forensics
  - Programming
tags:
  - bash
  - linux
  - scripts
---
2016-04-12 Update: Removed link to script. It will be published later as an update.

Recently, I had a large number of files which contained many duplicates. To reduce the number of files I had to view, I needed a way to remove all duplicates. In all likelihood, there are many tools available which can do this; however, I enjoy piddling with scripts. The following bash script, Unique Rename (urename.sh), renames each file to it&#8217;s MD5 hash. Duplicates are naturally removed as they overwrite the previous file. Simply drop the script into the directory and run it. File extensions should be reserved in most instances. The script automatically removes itself afterwards and prints some tallys at the end to show the number of files it removed.

I would like to flesh it out some more to utilize multiple cores/CPUs as md5deep only taps one at a time. Ideally, instead of overwriting the previous file, the move should silently fail to reduce extraneous writes. That said, here is the script as it currently stands.

Download: urename.sh
