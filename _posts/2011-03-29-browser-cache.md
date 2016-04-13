---
id: 85
title: Browser Cache
date: 2011-03-29T09:16:45+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=85
permalink: /browser-cache/
categories:
  - Forensics
tags:
  - artifacts
  - browser
  - cache
  - web
---
I recently learned that I had a flawed understanding of browser caching. My thought stemmed from two areas: the client and HTML meta entries. The client could toggle caching on or off with varying degrees of success. There is also the addition of private browsing modes which, again, work with varying degrees of success. With regards to meta entries, it was my belief these values tended to check the freshness of local caches to determine if rendering could simply use that or if the browser would have to request new content from the server.

However, based on a question on the HTCC mailing list regarding a lack of cache present when numerous hits were found in the index.dat file, I was reminded of and learned two critical pieces of information. For one, HTTPS connections are not cached. From a logical point of view, this should have been an obvious consideration. The second however is based on the HTTP protocol itself. There are settings at this level which can prevent the storage of cache. Granted, it depends on browser implementation, but it appears as though MSIE, Firefox, and Chrome adhere to (at least some of) them reasonably well. The [Caching Tutorial](http://www.mnot.net/cache_docs/#WORK "A tutorial on web cache for web administrators") covers different aspects of caching as well as a link to [REDbot](http://redbot.org/ "A reporting engine for displaying the HTTP request response") which displays the request header. Interesting, useful, and something new.

**TL;DR**

Read the [Caching Tutorial](http://www.mnot.net/cache_docs/#WORK "A tutorial on web cache for web administrators") to better understand the different methods of caching.