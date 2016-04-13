---
id: 76
title: Underworld Dreams Script
date: 2011-03-06T12:45:00+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=76
permalink: /underworld-dreams-script/
categories:
  - Games
tags:
  - muds
  - script
---
2016-04-12 Update: Removed link to script. This will be added to a repo.

I like to grab information from a terminal instead of opening a browser and waiting on &#8220;long&#8221; load times. Scrapping data into a terminal allows for additional, automated processing to occur on the results which can lead to interesting creations beyond the original author&#8217;s idea. During a break from playing [Underworld Dream](http://dreams.daestroke.com/ "Homepage for Underworld Dreams, an online MUD.")s, I found myself checking different status pages to keep up with activity. Instead of relying on auto-opening a browser tab, I decided to whip up a [little Perl script](/content/scripts/udgrep.pl "Perl script for pulling down Underworld Dreams statistics") (right-click and save) and take the time to learn the basics of [LWP](http://search.cpan.org/%7Egaas/libwww-perl-5.837/lib/LWP.pm "CPAN page for the World Wide Web Perl library."). It should work in both Windows and Linux, but I am sure it can be improved upon. If you wish to use it in Windows, be sure to use [ActiveState&#8217;s ActivePerl](http://www.activestate.com/activeperl "Homepage for ActivePerl, a Perl port for Windows").

Below is the help syntax:

<pre>Usage: udgrep [options]
Options:
  -w     -- Extract the current WHO list
  -n     -- Extract the recent news
  -c     -- List all active clans
  -h     -- Retrieve help information
  -l     -- Retrieve an active poll list
  -s     -- Retrieve stats page
  -d     -- Retrieve dev pages
  -p     -- Lookup a specific player</pre>

**TL;DR**

Here is a little Perl script for accessing Underworld Dreams&#8217; statistics, udgrep.pl.
