---
id: 288
title: Update and Book Review
date: 2013-09-22T09:15:33+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=288
permalink: /update-and-book-review/
categories:
  - News
  - 'Test &amp; Review'
tags:
  - book
---
Firstly, it has been a while since I&#8217;ve updated anything here. I have updated the Links page to clean out the stale and, most importantly, to add David Cowen&#8217;s blog &#8220;[Hacking Exposed &#8211; Computer Forensics Blog](http://hackingexposedcomputerforensicsblog.blogspot.com/ "Hacking Exposed - Computer Forensics Blog")&#8220;. David has been putting up a tremendous number of articles and hosts a lunch webcast every Friday at noon central. Guest speakers are encouraged to respond and give a brief talk, but David Cowen and Matt Seyer hold their own just fine when interaction drops.

Now for the book review. I am a bit of a sucker for cheap and short books on staying anonymous. The latest disaster is &#8220;[How to be Anonymous Online](http://www.amazon.com/dp/B00BDVBGQC "Amazon product page for book")&#8220;. The book really does not live up to its name, but that&#8217;s expected for a $5 purchase weighing in at 35 pages. If it had a table of contents, it would look like this:

  * Obtaining TAILS
  * Burning TAILS
  * Configuring TAILS
  * Installing TAILS to USB
  * Anonymous Email
  * Setting Up PGP
  * Using PGP
  * Updating TAILS
  * Bitcoins

Upon closer inspection, the majority of the book revolves around [TAILS](https://tails.boum.org/download/ "TAILS Download Page"). The Amnesic Incognito Live System (&#8220;TAILS&#8221;) is a TOR enabled, Linux LiveCD. Their download page covers everything that the book covers, even setting up persistent volumes. The page also links over to a [documentation page](https://tails.boum.org/doc/index.en.html "TAILS documentation"). It&#8217;s at this point that the author starts laying down &#8220;fact&#8221; without any references to support their claims.

The first issue lies in persistent volumes. If one it attempting to be as anonymous as possible, as the book leans towards, then having persistent data is far from ideal. The author does acknowledge that the volume is encrypted, but seems to be satisfied with &#8220;it&#8217;s encrypted.&#8221; TrueCrypt is not mentioned at all; only the magical and unnamed system (LUKS in this case).

The coverage of PGP is nice, but PGP has been covered many times and the TAILS documentation page does an adequate job. Webmail was mentioned and a link provided to the author&#8217;s blog which lists webmail services that do not require confirmations, uses no Javascript, and allows for TOR connections. This is nice, but there is no mention of the Claws mail client. Using a standalone client has its own issues, but it does avoid the Javascript issue after the account has been created. In fact, in the author&#8217;s checklist for creating a persistent volume, they include having Claws store emails to that volume.

Javascript is its own issue. Iceweasel (Firefox), the default browser, makes use of the NoScript addon. TAILS mentions that the use of Javascript is a compromise between functionality and security. Since many sites require Javascript to render, it is a decision that should be left to the user and not a mandate from an author without explanation. The author disables Javascript from the browser which will impact the toggling of features via NoScript and the TOR Button. This will be problematic for some users. No mention is made of offline caching, such as that used by HTML5. This is why education and not checklists are key to security and anonymity books.

And that&#8217;s where the book falls hard. The re-publishing of the TAILS documentation, mention of Plop Boot Manager without any discussion of Plop, or the flat statement that Bitcoin is not anonymous are bad. But, anonymity is not about being absent and leaving no trace as the book suggests. It is about not revealing the true identity. Learning to minimize one&#8217;s tracks and to misrepresent what is left is key. The book does not delve into this point with any recognition or authority.

In short, use TAILS. Use their documentation to get up an running. But, follow up with more education and know that software can not fix wetware (your thinking and habits) mistakes. Anonymity requires conscious actions that deviate from our typical human interactions.