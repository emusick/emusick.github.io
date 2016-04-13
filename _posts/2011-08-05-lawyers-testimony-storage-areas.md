---
id: 102
title: 'Lawyers &#038; Testimony &#8211; Storage Areas'
date: 2011-08-05T09:03:52+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=102
permalink: /lawyers-testimony-storage-areas/
categories:
  - Forensics
tags:
  - lawyers
---
I am a fledgling when it comes to forensics and testifying, but I want to start a series of articles &#8220;Lawyers & Testimony&#8221; about my experiences. Instead of rehashing events, I want to give a really basic understanding of issues I have run across. Ideally, this is meant to assist those testifying by giving them a way to explain topics. It should also help attorneys in understanding how to proceed in questioning and provide a common ground between the technical side and the layman side.

In preparing for court, one of the attorneys was going over how they would be introducing the evidence. They wanted to go along the lines of:

  * (give me the laptop)
  * Is this the computer you examined?
  * (compare serial numbers)
  * Yes, it is.
  * What did you find on this computer during your examination?

That seemed all good and fine, except I started to question what did I actually examine? A computer is not a single item; although, it is very convenient to think of it that way by most people. A computer is made up of multiple components that work together. When it comes to an examination and testifying, &#8220;computer&#8221; is not specific enough in my opinion.

When it comes to forensics, there are three main areas that are reviewed for evidence: [CMOS](http://en.wikipedia.org/wiki/CMOS "Wikipedia description of CMOS"), [RAM](http://en.wikipedia.org/wiki/RAM_memory "Wikipedia description of RAM"), and [Hard Drives](http://en.wikipedia.org/wiki/Hard_drive "Wikipedia description of hard drives"). There are other areas potential evidence may be found, other devices, etc. But, these three represent the areas most commonly reviewed.

The CMOS is often times (incorrectly) referred to as the [BIOS](http://en.wikipedia.org/wiki/BIOS "Wikipedia description of BIOS"). The BIOS (Basic Input/Output System) identifies input (keyboard, mouse, etc) and output (video card, etc) components and devices. This identification process occurs when a computer is first powered on. The CMOS (Complimentary Metal-Oxide Semiconductor) stores basic information about the system and BIOS. In particular, system time, power-on passwords, and boot order are three pieces of information typically garnered from the CMOS.

RAM (Random Access Memory), or simply &#8220;memory,&#8221; is a holding area for data while it is being processed. It can contain processing instructions, file contents, and temporary data. The problem with RAM is its volatility &#8212; data present in memory does not persist when power is removed. As such, memory must be acquired while the system is still powered on (technically, data is lost as its charge is lost and, if acted on quickly or with special tools, can be recovered outside of the system after it has lost power).

Hard drives are the primary storage locations within a computer system. They are meant to retain large amounts of data without the need to maintain power. When people say they examined a computer, they are most likely referring to the hard drive associated with that computer. Hard drives are typically removed from the computer and processed as a separate item. This allows the examiner more flexibility, especially as it relates to write protection. By splitting it from the computer chassis, it can be addressed by itself or as a component of the computer. In my workplace, our reports generally follow along the lines of:

> The following items were received at the Computer Forensic Lab:
> 
> AgentInitials-E1 &#8211; Dell Latitude laptop SN: XXX123YYY456 which contains,
> 
> AgentInitials-E1a &#8211; Seagate XX12YY34 SATA 300GB HDD SN: XXX123YYY456
> 
> AgentInitials-E2 &#8211; Lexar 4 GB USB thumbdrive SN: XXX123YYY456

What does this mean for the above line of questioning? It means that after establishing that the computer serial number was submitted as evidence, the hard drive must be identified as a component of that computer. Compare its serial number and proceed with &#8220;what was found on the examined drive&#8221; or similar approach. Remember that a computer may contain multiple hard drives and should have separate evidence numbers to distinguish them. Most all hard drives should list a vendor name, model number, serial number, and other information that can be used to identify it.

The above is not meant as rant and hopefully it sets a foundation of understanding for someone. In my experience, most people understand that a computer is not a magical item and that it is comprised of multiple pieces. Most people do not necessarily understand the underlying hardware, but they are aware that it exists. Unfortunately, glossing over the concept of a &#8220;computer&#8221; does not help the explanation process. Clear articulation and a basic understanding can go a long way in improving communication between practitioners, lawyers, judges, and jury.

**TL;DR**

Forensic practitioners do not examine computers. They examined specific components contained within the computer system; the most common being the CMOS, RAM, and hard drives. Being too abstract causes confusion and being too verbose can be boring. Shoot for the middle ground, using appropriate terminology and add more details as required.