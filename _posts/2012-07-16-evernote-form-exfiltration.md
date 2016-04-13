---
id: 206
title: Evernote Form Exfiltration
date: 2012-07-16T20:50:57+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=206
permalink: /evernote-form-exfiltration/
categories:
  - Productivity
  - Security
tags:
  - evernote
  - scam
---
Given the community support of Evernote and the frequent sharing of notebooks, notes, and templates, I began thinking of ways that user data may be exfiltrated. In particular, I was interested in whether form data could be sent offsite.

The first part of this exercise was benign in that I wanted to create a drop-down selection menu to assist in inputting data. After writing the raw HTML into an ENEX file and importing it into Evernote, the form displayed correctly. Since no back-end existed to save this information, each time the note was reload it reverted back to the first entry.

Knowing that forms could be displayed and being curious about exfiltration, I created a Google Docs form and asked for the embed code. This is meant for placing the form into web pages and it loads inside an IFRAME. Pasting this into an ENEX file and importing was neat and scary; it worked. Presented in the blank note was the Google Docs form after a short load time. The submitted results were populated and graphed out using Google Docs&#8217; own results page.

The note containing the IFRAME code will result in an sync error and be deleted. If other text is present along with the IFRAME code, the note contents will be deleted, but the note will be still be present.

This raises a couple of issues. One is that exfiltration can happen, but the method needs to refined for it to be really useful. The second is two-fold with IFRAMES. On one hand, user tracking is possible as each outbound call will leave a nice log for the third party to retrieve. The second part is the ability for a third party to inject content into loaded notes. While this concept may at first seem silly, it is the entire premise of ad supported widgets. If a third party was more insidious, they could inject some Not Safe For Work content that may raise more than eyebrows.