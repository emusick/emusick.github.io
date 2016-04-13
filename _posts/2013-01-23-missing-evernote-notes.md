---
id: 271
title: Missing Evernote Notes
date: 2013-01-23T15:46:44+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=271
permalink: /missing-evernote-notes/
categories:
  - HowTo
  - Productivity
tags:
  - evernote
---
I recently had an issue with Evernote in which the Windows Desktop client was showing 350 fewer notes than were present on the Android and Web clients. After the initial panic subsided some, I sought to get a clean slate to correct my local database corruption. The actual corruption itself appeared to be the result of a buggy pre-release which I had opted into when first trying Evernote. I high recommend opting out of this for stability purposes. One can check their installation via &#8220;Tools -> Options -> General -> Update to pre-release version when available&#8221;. The steps I performed for my clean slate are listed below.

  1. Empty Trash before exiting Evernote
  2. Un-install Evernote
  3. Delete database
  4. Re-install latest stable Evernote
  5. Perform new sync

One probably only needs to exit Evernote, delete the database, and re-sync, but as I wanted to downgrade, this was the best approach. Trash files are synchronized back and forth. Unless there is a strong reason to retain these, the fresh sync can be sped up significantly (potentially) if they are removed prior to sync&#8217;ing. I ended up with five fewer notes than originally expected, but these were the last five I had deleted. For some reason, the changes had not visually refreshed on my other clients so this did not result in an actual loss. My nested tags required a second sync for them to appear properly.