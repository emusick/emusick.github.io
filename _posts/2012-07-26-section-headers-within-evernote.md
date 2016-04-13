---
id: 211
title: Section Headers Within Evernote
date: 2012-07-26T23:00:46+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=211
permalink: /section-headers-within-evernote/
categories:
  - HowTo
  - Productivity
tags:
  - evernote
---
Evernote allows, at least indirectly, users to modify the underlying code used to display notes. This raw code is actually HTML. While some attributes like anchor names cause sync failures, other elements like tables work as expected. Evernote&#8217;s parsing engine requires proper structure and has some quarks.

Without the ability to use name attributes for anchor elements, it is difficult to create internal linking for a table of contents. This prompted the creation of nice looking section headers that would stand out while scrolling. The sample below was created using tables. This is not proper for HTML on the Internet as it confuses text readers and fails to meet certain accessibility standards, but it will work for the purposes here.

The below code uses CSS styling of HTML elements to achieve its appearance. The TBODY element is not required, but it does not hurt to have it. The non-breaking space entities are required however. Evernote does not like empty tags and will refuse to sync the note. This is applicable in other areas for manually hacking notes.

Aside from changing the content, colors, and typeface, the below code should serve as template. Enjoy and modify to taste.

<img title="EvernoteSectionHeaders" src="/resources/EvernoteSectionHeaders.png" alt="Section header" /></a>

Section Header example

**Raw Code:**

<pre>&lt;table style="border-collapse:collapse; width:100%"&gt;
    &lt;tbody&gt;
    &lt;tr&gt;
        &lt;td style="width:50px; padding:0px 5px; background-color:#99CCFF; color:#F0F0F0; text-align:center; font-size:36px;"&gt;1&lt;/td&gt;
        &lt;td style="padding:0px 10px; background-color:grey; color:#F0F0F0; color:#F0F0F0; font-size:24px;"&gt;Section 1 Title&lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr style="height:5px;"&gt;
        &lt;td style="background-color:#99CCFF;font-size:0px;"&gt;&nbsp;&lt;/td&gt;
        &lt;td style="background-color:#FF6633; font-size:0px;"&gt;&nbsp;&lt;/td&gt;
    &lt;/tr&gt;
    &lt;/tbody&gt;
&lt;/table&gt;</pre>
