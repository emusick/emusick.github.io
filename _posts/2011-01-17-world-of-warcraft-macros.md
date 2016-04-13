---
id: 57
title: World of Warcraft Macros
date: 2011-01-17T10:18:50+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=57
permalink: /world-of-warcraft-macros/
categories:
  - Games
tags:
  - script
  - world of warcraft
---
My [current UI](http://www.flickr.com/photos/emusick/5314445469/ "My current DPS interface for World of Warcraft") does not display XP which prevents the masochistic nature of checking XP til-next-level instead of actually leveling. So, a friend threw out the following macro.

<pre>/script ChatFrame1:AddMessage(string.format("XP to next level: %d",(UnitXPMax("Player")-UnitXP("Player"))))</pre>

He also threw out a neat speed macro which reports your character&#8217;s current travel speed.

<pre>/script ChatFrame1:AddMessage(string.format("Player Speed: %d%%",(GetUnitSpeed("Player")/7)*100))</pre>

Both macros are single lines, so make sure when entering them that the line is not split.

User comment by Drey:

> [&#8230;] the character pane, as of 4.0.6, now shows you what your maximum speed in your current form / on your current mount ought to be. The macro is still useful for seeing what speed you actually \*have\* however; before patch 4.0.6, druids weren&#8217;t getting the correct speed modifiers in flight form.