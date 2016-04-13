---
id: 233
title: 'World of Warcraft &#8211; LUI Customization (Part 2)'
date: 2012-10-01T17:04:20+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=233
permalink: /world-of-warcraft-lui-customization-part-2/
categories:
  - Games
tags:
  - world of warcraft
---
In the [previous post](http://erikmusick.com/world-of-warcraft-basic-layout-part-1/ "World of Warcraft – Basic Layout (Part 1)"), I discussed my transition from point-and-click to hotkeys and from creating my own layout to using a compilation pack. The compilation pack that I chose was [LUI](http://lui.maydia.org/ "LUI compilation pack homepage") after browsing through [Vranx](http://www.vranx.com/ "Vranx homepage"). Its sleek look and feature set was the main appeal. I was much more impressed after installing. The built-in configuration menu and custom code instead of simply unpacking other addons was a pleasant surprise.

Before making any changes, I like to load all of my addons to make sure that at least work in a default state. Since LUI does a great job handling so many features, I have only added five addons: AuctionLite, Bagnon, BoP Remove, Postal, and Prat (all available on [Curse](http://www.curse.com/addons/wow "World of Warcraft addons on Curse.com")). AuctionLite and Postal are quality of life enhancements that make dealing with the auction house bearable and being able to bulk process the mail inbox. BoP Remove disables the &#8220;Are you sure you want to loot this BoP item&#8221; message that is quite irritating on a single account, much less on two or more. Bagnon is handy for the added tooltip informing players which characters have the selected item and how many. LUI handles gold accumulations which is part of Bagnon, but it does not yet handle caching character&#8217;s bags. Prat is straight forward and can be customized to taste.

BoP Remove requires some minor configuration upon loading. Players can set the quality threshold and party size. Personally, I set mine to epics and 40-man raids to hide all BoP messages. After making the appropriate changes, click the &#8220;X&#8221; button to hide the frame. Bagnon can be modified to taste. I tend to scale bags to 70% and banks to 80%, remove the data broker frame, and hide the gold count (LUI does a better job). There is a sixth addon that I will discuss in the next article as it relates directly to multi-boxing; Jamba.

## Configuring LUI (/lui)

I made minor changes to the default LUI configuration. Below they are itemized, but essentially I&#8217;m hiding the micromenu bar from being shown every login, turning off the bag and interrupt announcements, and enabling the Focus Target.

General -> Settings

  1. Uncheck &#8220;Show micromenu&#8221;
  2. Check &#8220;Hide Talent change spam&#8221;

Bags -> Bags

  1. Uncheck &#8220;Show bag bar&#8221;
  2. Check &#8220;Show item quality&#8221;

Bars

  1. Right Bar 1 
      1. Check to show
  2. Left Bar 1 
      1. Check to show

Modules

  1. Disable Bags
  2. Disable Interrupt Announcer

Tooltip -> Settings

  1. Check &#8220;Anchor to cursor&#8221;

Unit Frames

  1. Focus Target 
      1. Check &#8220;Enable&#8221;

## Configuring Bartender (/bt)

Once LUI has been configured, I set up my action bars. Based on the hotkeys mentioned previously, I place the appropriate skills in the slot and add the correct hotkey. I like having the hotkey characters displayed so I enable those. I use Bar 4 for hidden skills such as pet and mount summons. Bar 6 will actually be hidden behind LUI&#8217;s &#8220;Right Bar 1&#8221; and Bar 9 will be &#8220;Left Bar 1.&#8221; These are hidden bars that are accessible as a pull-out menu. On the right bar, I like to have pet functions and buffs. On the left bar, I currently have potions and food, but I may get rid of this bar in the future and simply open my organized bags. My first row of bags follow the same outline as action bar 9.

Bar 1

  1. Uncheck &#8220;Hide hotkey&#8221;

## Configuring Skills

Action Bar 1

  1. Basic attack (hotkey: 1)
  2. Basic attack (hotkey: 2)
  3. Instant cast (hotkey: 3)
  4. Proc attack (hotkey: 4)
  5. Nuke (hotkey: F)
  6. Racial, CC break, or Trinket/Burn (hotkey: Mouse-Button-5)
  7. AoE (hotkey: 5)
  8. Curse, stun, or DoT (hotkey: C)
  9. CC (hotkey: Q)
 10. Silence of Fear (hotkey: E)
 11. Proc attack (hotkey: R)
 12. Situational (hotkey: T)

Action Bar 4

  1. Temporarily disable &#8220;Always hide&#8221; under &#8220;Visibility&#8221;
  2. mount (hotkey: F12)
  3. Re-enable &#8220;Always hide&#8221;

Action Bar 6

  1. Buffs / Pets

Action Bar 9

  1. Bandage
  2. Health potion
  3. Mana potion
  4. Healthstone
  5. Food
  6. Misc potion
  7. Aspect / Auras

## General LUI Tips

After the initial installation of LUI, some of the frames will probably overlap. To toggle all frames, click the sparkling ball in the top center of the screen. Unlock chat and party frames to drag them into place. Omen and Recount must be unlocked through their addon configuration menus. Once unlocked, drag them into place and re-lock.

Experience to next level is available for mouse hovers just under the player resource bar. Clicking on the information will print it to the current chat channel or directly to the chat frame (essentially, a private message only visible to you).

Follow on to [Part 3 &#8211; Multiboxing](http://erikmusick.com/world-of-warcraft-dual-boxing-part-3/ "World of Warcraft – Dual Boxing (Part 3)").
