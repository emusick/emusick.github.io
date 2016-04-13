---
id: 168
title: Forensic Intelligence
date: 2011-11-07T21:07:29+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=168
permalink: /forensic-intelligence/
categories:
  - Forensics
  - Programming
tags:
  - script
  - windows
---
In the past two years since beginning forensic work, I have wanted to convert my [incident response scripts](http://erikmusick.com/live-response-scripts.html "Live Response Scripts") to a system that could do much of the grunt, preview work for me; particularly, getting browser history dumps and basic registry information for report writing. I have also wanted to give PowerShell a whirl. Unfortunately (not surprising), I discovered that I PowerShell is not a flexible way to distribute scripts. It is amazingly good for IT work.

That said, I want to go ahead an upload the PowerShell version. While it is rough and only supports one external call, it should give a clear idea how the new version will function. Hopefully someone will also find the code useful. I do looking forward to Harlan Carvey releasing his [forensic scanner](http://windowsir.blogspot.com/2011/10/forensic-scanner.html "Harlan Carvey's Forensic Scanner").

Forensic Intelligence: [forint.ps1](/content/scripts/forint.ps1 "Forensic Intelligence script, forint.ps1")