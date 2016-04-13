---
id: 21
title: Creating Thumbnail Indexes
date: 2010-11-30T10:19:59+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=21
permalink: /creating-thumbnail-indexes/
categories:
  - Programming
tags:
  - batch
  - script
  - windows
---
There does not appear to be a great number of free utilities that run from the command line (or support batch processing) on MS Windows to generate thumbnail indexes. When dealing with a vast number of movies, instead of viewing each one independently, it may be beneficial to export them all and create snapshots at certain intervals. Then an image viewer could be utilized to quickly identify suspect videos. Even better would be to create a composite image that contains all snapshots for a specific file. Enter, [Movie Thumbnail](http://moviethumbnail.sourceforge.net/ "Homepage for Movie Thumbnail") (MTN).

Notice in the second paragraph that a mplayer command is given for Linux. Unfortunately, MS Windows appears to lack such luxuries without a bit of hassle. MTN is lightweight and does not need to be installed. The commands for it can become cumbersome, especially when handled by many investigators. So, below is a simple batch file which can be modified as needed. By default, MTN is run from the same directory as the movies. The created images are five by four snapshots and have &#8220;_ASP&#8221; appended to the end to signify they were generated.

<pre>:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::
::
:: Author: Erik Musick
:: Version: 0.2
:: Date: 2010.02.26
::
:: Changelog:
::     2010.04.22 v0.2 - Added -P to remove pause
::
:: Purpose: Send-To launcher for MTN
::
:: Syntax: mtn.bat 
::
:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

@ECHO OFF
"%~dp0\mtn.exe" -c 5 -r 4 -P -o _ASP.jpg -j 60 %1</pre>

When iterating over an entire directory of movies, a little FOR loop may be useful.

<pre>for /F "usebackq tokens=*" %i in (`dir /B`) do @mtn.bat "%i" >> logfile.txt</pre>