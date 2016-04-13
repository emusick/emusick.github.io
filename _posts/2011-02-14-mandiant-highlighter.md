---
id: 72
title: Mandiant Highlighter
date: 2011-02-14T23:09:43+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=72
permalink: /mandiant-highlighter/
categories:
  - Security
  - 'Test &amp; Review'
tags:
  - logs
---
In a rash of downloading recently, I grabbed a copy of Mandiant&#8217;s [Highlighter](http://www.mandiant.com/products/free_software/highlighter/ "Production description page for Highlighter, a text manipulation tool"). Although Mandiant provided a description, I was not left with a clear idea of what it did. Instead of caution, it was installed and poked. The interface is about as bland as a plain ham sandwich. However, a lot of interesting things crawl beneath the surface. This is a poor review, but hopefully it will serve as a mediocre introduction.

The basic premise of the application is to enable users to quickly highlight text. How surprising given the name. One interesting part is the pane on the right side of the window. This portal contains a view of the entire document. The tiny size is not meant to be read, but rather provide a way to interpret the text. Instead of focusing on words, the user can identify patterns; locations within the file that recur over different sections. Noise (irrelevant lines) can be stripped out by selecting the undesired text and right-clicking to bring up the context menu.

The context menu is fairly straight forward until the &#8220;Field Operations&#8221; section. This allows the user to define the format of the text (ie. comma delimited, tab delimited, or a user defined delimiter). While any text can be viewed and toyed with, the delimiters bring the geeks to the yard; especially the pre-defined Apache option. These delimiters help parse the file which enable &#8220;Uniquely Highlight Values&#8221; (UHV) and histogram functions. UHV can take a column (say, the third column in a semi-colon delimited file) and highlight each unique value with a unique color. For instance, all &#8220;Fu&#8221; are red, &#8220;Bar&#8221; are blue, etc. The histogram function relies on setting a field as a date or time. Highlighter will automatically sort the data into a chronological order with time along the X-axis and the number of occurrences along with Y-axis.

Is this something you want to use all the time? Probably not. Is it handy for quickly going through logs? Sure. If you find yourself trolling over the same structure, take advantage of the &#8220;States&#8221; which can save a set of highlight and remove options and apply them to future files. It definitely seems to to be more applicable analyzing anomalies over time, but it could have some interesting uses beyond that. The included PDF located in the install directory is quite useful (accessible from Help -> Help Contents). It also appears that Highlighter will run after it has been uninstalled. Simply copy the install directory to a mobile device prior to uninstalling and you have a new portable application.

**TL;DR**

Highlighter is an interesting tool for graphically analyzing patterns in text files; particularly chronological logs. The installed package is 4.43 MB (with documentation; 581 KB executable). Play with it and see if you have a use for it.