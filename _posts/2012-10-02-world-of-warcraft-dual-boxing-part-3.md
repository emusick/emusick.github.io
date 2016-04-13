---
id: 241
title: 'World of Warcraft &#8211; Dual Boxing (Part 3)'
date: 2012-10-02T10:16:45+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=241
permalink: /world-of-warcraft-dual-boxing-part-3/
categories:
  - Games
tags:
  - world of warcraft
---
Continuing from the previous two articles ([Basic Layout](http://erikmusick.com/world-of-warcraft-basic-layout-part-1.html "World of Warcraft – Basic Layout (Part 1)") and [LUI Customization](http://erikmusick.com/world-of-warcraft-lui-customization-part-2.html "World of Warcraft – LUI Customization (Part 2)")), this last part deals specifically with the dual box configuration. Before switching to LUI, I attempted to use [AutoHotkey](http://www.autohotkey.com/ "AutoHotkey homepage") as a free method to broadcast keystrokes to a second window. This worked, technically, but it was far from ideal; partly because AHK is a generic broadcaster with no built-in intelligence for games. I grabbed a [basic configuration file](http://www.autohotkey.com/community/viewtopic.php?t=33704 "AutoHotkey basic configuration file") from AutoHotkey&#8217;s own forums and modified it to support my hotkeys ([my config](content/scripts/AutoHotkey.ahk "My AHK file")). Although it supports key modifiers, it is obvious that macros are even less ideal when multi-boxing. It is difficult to see proc messages, time abilities, and generally keep up with anything but the most basic of action.

One major drawback was that without window management or maintaining two copies of the game folder, only one window was visible at a time. Often times, I would get wrapped up in questing and I would not realize that my second account was no longer following the main account. This also makes it impossible to see proc messages, aggro warnings, etc. It was also slightly surprising to see how difficult navigation is for followers and how important jumping is. Without setting a separate hotkey for follower jumping, it was difficult to get over some hurdles. Essentially, mere key broadcasting is not enough. Multi-boxing requires some flexibility and intelligence.

## ISBoxer

Going back to [WoW Wiki](http://www.wowwiki.com/Multiboxing_software "WoW Wiki page for multi-boxing software"), I found and signed up for a week trial of ISBoxer. I strongly encourage anyone interesting in multi-boxing to at least take the trial. The application is weird and it does take some configuration to get it &#8220;just right,&#8221; but it is a great starting point even if you decide on another product. ISBoxer handles window management so that multiple instances of Warcraft can be displayed at once. It also allows for hot-swapping between instances to bring a slave to the primary monitor. It creates character specific Config.WTF files so that multiple accounts can be run from the same game folder without conflict. Some default hotkeys and game logic is included for Warcraft; including a slave jump combination.

ISBoxer can also broadcast mouse movement. This makes loot rolls and quests much easier to navigate. I am still having difficulty in getting AoE attacks to work without swapping windows, but it is supported once configured correctly. Now that I was able to handle characters getting feared and being able to swap and continue attacking among other tasks while I re-acquired my feared character (Alt-F), my next bottleneck become slaves breaking follow during combat. Originally, I was playing ranged classes and did not notice the problem. However, once I rolled melee Monks, the issue became a deal breaker. Each time a melee skill is used, follow is broken. This means that during combat, players will be constantly re-acquiring follow to reposition themselves better. Fortunately, this sounds worse than it really is and eventually becomes a graceful finger dance across a keyboard stage. We can ease this dance quite a bit (along with lessening Repeater toggling) below when we look at Jamba.

As far as configuration is concerned, read their [Quick Start Guide](http://isboxer.com/wiki/WoW:Quick_Start_Guide "ISBoxer's quick start guide") and follow the wizards. Under Keymaps, I copied &#8220;DPS 1&#8221; and changed the relevant areas to support my alpha keys. The two areas that must be changed are &#8220;Hotkey&#8221; when selecting &#8220;DPS 1&#8221; and the &#8220;Key combination&#8221; under &#8220;Steps&#8221; and &#8220;1 -> all&#8221;. This sounds confusing, but it allows for a single WoW hotkey to issue different keystrokes to different windows. If using a consistent action bar as I do, then these two sections should be the same.

Aside from configuring Keymaps, the only two changes I have made is to reposition the Keymap and Repeater &#8220;[click bar](http://isboxer.com/wiki/Click_Bar "ISBoxer wiki page for configuring click bars")&#8221; so that it does not cover my buffs. While in-game, limber up your fingers and enter the default In-Game ISBoxer GUI with Ctrl-Shift-Alt-G (this can be changed via the ISBoxer Toolkit). When this window is open, all created click bars are unlocked. I dragged mine towards the minimap and far just low enough to avoid the drop-down micromenu. Press Ctrl-Shift-Alt-G again to hide the configuration window.

The [FPS indicator](http://isboxer.com/index.php/guides/3-disabling-fps-indicator "Hiding and disabling the FPS indicator") sits right on top of LUI&#8217;s gold information text. Since LUI already displays FPS, I disabled this within the ISBoxer Toolkit. Select your Character Set and check &#8220;Hide FPS (framerate) indicator&#8221;. Export settings and enjoy. I have not experimented too much with the settings and that is good. It means that after informing ISBoxer of your hotkeys all that is left is to enjoy the game.

## Jamba

Now comes [Jamba](http://wow.jafula.com/addons/jamba/ "Jamba addon homepage"). This little addon is supported by ISBoxer and handles in-game team management, whisper forwarding, quest turn-in helpers, and much more. It also strobes follow commands so that characters are picked back up without a lot of manual tedium. Without strobing, Jamba does a noble job and greatly cuts down on manually acquiring follow. After configuring Jamba, it allows you to push settings to your entire team or load from a previous profile. Quest turn-ins are much quicker and my characters are able to stay on target better. Auto-accepting resurrections  auto-repairs, and auto-selling junk are all handy. There are a ton features packed into Jamba and I have only taken to a few surface changes. All of the settings will be preference as simply installing it will enable some auto-follow features.

**Downloading Note:** Download from WoW Curse, but ensure you are using the MoP beta version found under &#8220;Other Downloads.&#8221;

Below are the options that I have changed to give you an idea, but I highly suggest reading their Jamba website. They list everything and provide descriptions.

  * Auto Accept Invites
  * Auto Accept Friends Only
  * Auto Repair
  * Auto Sell Poor Quality Items
  * Forward Whispers and Relay
  * Take Master&#8217;s Taxi

I originally had &#8220;Warn if I stop following (slave)&#8221; enabled, but it will constantly ding on melee characters. With both WoW instances visible, I notice a lack of movement and respond accordingly. Health warnings are nice to have. In my case, my master character is the beefiest and holds any aggro. This protects my slave fairly well unless it is feared or I catch a roaming pack.

Now that Jamba is configured on a single character, go back to the main Jamba configuration page. Push settings to all members and get to playing.

## Basic Tips

Window layout allows for easy window swapping. This will is great for changing masters, but it also allows for opening all the necessary dialogs so that Jamba can work properly or selling junk. For quests, it does not matter which character opens the first dialog. Typically, I will open on master, accept on slave, open second quest on slave, accept on master, rinse, and repeat. This makes it fairly efficient to accept multiple quests. If click-to-move is used, they may be accessible with repeater enabled, but my slave always seem to be out of position (inherent in following) and I dislike click-to-move.

After being feared, it has been rare (so far), that a simple Alt-F did not bring the character back. If my character is out of range, I swap windows and continue spamming my attacks while I stroll back into action. This keeps my slave engaging targets while the master window takes a break.

Monk rolling breaks follow. While rolling, tap Alt-F and keep cruising.

Breaking follow is sometimes necessary, such as when tight-rope walking, doing vehicle quests, etc. To achieve this, toggle off Keymaps and Jamba&#8217;s strobe, if enabled. Characters will still auto-follow after screen swapping. Now is the time to use the pre-configured follower jump (default keybind is Ctrl-Space). Any slave movement will work, but slave jumping is already configured.

<del>Disable Jamba on un-teamed characters.</del> **Edit:** This section about disabling Jamba was incorrect. It&#8217;s best to just manage the team through Jamba&#8217;s configuration. If the character is running solo, just remove all names from the team listing.

Remember to toggle Keymaps off if using alpha hotkeys. Using Ctrl-Shift-M (default binding) before chatting will prevent bad pulls, flying off of cliffs, and your chats from looking like a cat ran across the keyboard. Considering how often you find yourself toggling, it may be more efficient to change the toggle hotkeys to something more manageable.

## Improvements and Troubleshooting

FPS: Shortly after MoP was released, I was suddenly getting atrocious FPS; around 10 FPS when dual-boxing. I spent a day going through settings and reading websites only to luck into a nVidia driver update.

Reloading ISBoxer changes: ISBoxer does not require WoW to be restarted before applying new changes. This means that while playing, changes can be made via the ISBoxer Toolkit. Simply perform the standard &#8220;Export All to Inner Space&#8221; and a message will appear on each instance of WoW stating that new changes have been applied.

Window Layout: Configuration is a matter of preference, but be sure to give ISBoxer enough time to load the windows before assuming that something is broken. I spent a week disappointed that I couldn&#8217;t hot-swap windows because after initiating my team, my slave window was not in its appropriate location. Knowing that ISBoxer keeps different Config.WTF for each character, I set out to &#8220;fix it&#8221; by changing the display options from &#8220;Primary&#8221; monitor to &#8220;Monitor 2.&#8221; Bad idea. If ISBoxer, after waiting, still is not displaying the layout correctly, go back and run the Window Layout Wizard again.