---
id: 98
title: 'F-Response Tactical: A Brief Review'
date: 2011-07-26T10:50:54+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=98
permalink: /f-response-tactical-a-brief-review/
categories:
  - Forensics
  - 'Test &amp; Review'
tags:
  - network
---
I had the opportunity to use [F-Response&#8217;s Tactical software](http://www.f-response.com/index.php?option=com_content&view=article&id=199&Itemid=82 "F-Response homepage for Tactical") while attending the Federal Law Enforcement Center&#8217;s (FLETC) Computer Network Investigations Training Program (CNITP). The software and dongles are easy to use on Windows platforms. The Mac version is fairly straight forward; although, there is no GUI for the suspect dongle. The GUI is handled from the Windows examiner dongle. The Linux version was a bit tricky. Vanilla Ubuntu had some permission errors, but Fedora Core seemed to work smoothly (again, no GUI from the suspect dongle).

The concept of having network drives mapped as a local device is great and is quite useful as some applications balk at using network shares. The two dongles are paired and will not pick up the broadcasts from other dongle pairs in use. Working primarily with Internet Crimes Against Children (ICAC) cases, the absence of encryption between the dongles is unfortunate. All transfers between the two machines is plain text and easily sniffed. When dealing with contraband data, this becomes problematic.

For quick and easy access to machines, F-Response is great. Particularly in the environment focused on by the CNITP class; networked. Plug one dongle into the server or workstation and take the other one with you to a warmer, less noisy room to conduct your work.

**TL;DR**

Overall, a nice idea and it works well. The lack of encryption may be a problem; hopefully, newer versions include default encryption.

**Update (August 07, 2011):**

I just ran across Chad Tilbury&#8217;s article [F-Response Tactical](http://forensicmethods.com/f-response "Review of F-Response Tactical by Chad Tilbury") which covers how the tool is used and some basic pros and cons.

**Update (August 10, 2011):**

I had the opportunity to speak with Matthew Shannon of F-Response yesterday. He was interested in discussing my concerns about encryption. Even across the phone, he came off as energetic and excited to see how F-Response might make a better product. It was refreshing to hear from such an active company.

I have also had a few other responses to the article and I want to take them time to add a bit more back story. The initial concern that was voiced over using a tool such as F-Response&#8217;s Tactical tool was the lack of encryption when dealing with contraband data. The mere possession of the types of files we work with in child exploitation cases is a criminal offense. Mitigating the dissemination of these files is just as critical as it is to identify them and their possessors. The impact of leaking this data is two-fold. One is the possibility of distribution of child exploitation materials. The other is the impact on the victims portrayed in the materials.

By utilizing encryption, the risk associated with accessing and transferring these files across a potentially open network decreases dramatically. However, I did not touch on the practical side of this and I was made aware of that during my talk with Mr. Shannon. In most situations, the forensic acquisition would occur over a switch or router. The network itself, in this case, adds a protective layer as the hardware ports are not open to other ports. Can an attacker make this possible? Of course. In most residential environments, is there going to be someone actively sniffing the network? Probably not. In a larger network within a corporate infrastructure? Possibly. If the concern is with malware, then the assumption must be made that the content has already be accessed and the introduction of Tactical will not further compromise that scenario.

The point is, during the process of a practical acquisition, the encryption requirements are not as absolute as they are in theory. Knowing that Tactical does not encrypt data is useful information. As with any situation, apply the best tool for the job. The same mental hurdle must be jumped for Tactical as it must for any form of live forensics. That said, F-Response offers a number of options beyond Tactical. The next version of Enterprise (at least) should include encryption if it is a mandatory requirement.

As a side note, this article has been mentioned on F-Response&#8217;s [reviews page](http://www.f-response.com/index.php?option=com_content&view=article&id=306:new-tactical-reviews-&catid=34:blog-posts "F-Response's review page for Tactical"); as well as Chad Tilbury&#8217;s.

**Update (October 26, 2011):**

I had the opportunity to employ Tactical in a network environment recently. Super easy and &#8220;just worked&#8221;. I was able to attach to multiple machines, triage them quickly, identify two target machines, and image the drives. Could not have been any easier considering one of the machines was an Acer One which is not a joy to disassemble.