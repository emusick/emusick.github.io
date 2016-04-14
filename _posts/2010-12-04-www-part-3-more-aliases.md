---
id: 33
title: 'WWW &#8211; Part 3, More Aliases'
date: 2010-12-04T21:03:25+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=33
permalink: /www-part-3-more-aliases/
categories:
  - Games
tags:
  - muds
  - script
---
This is going to be a quick post following up [Part 2](http://erikmusick.com/www-part-2-aliases/), but it will demonstrate the usefulness of the **showme** command, how color works, and how to keep your enhancements straight. Let&#8217;s just jump right into the code and get to the explanations afterwards.

<pre>#class {cl_help} {kill}
#class {cl_help} {open}

#nop 0 - Black       5 - Magenta
#nop 1 - Red         6 - Cyan
#nop 2 - Green       7 - White
#nop 3 - Yellow      8 - Skip
#nop 4 - Blue        9 - Default

#nop ###################################
#nop ## Help lists
#nop ###################################

#alias {thelp} {#showme &lt;149&gt;==        &lt;229&gt;LISTS&lt;149&gt;        ==&lt;088&gt;;
#showme &lt;149&gt;=========================&lt;088&gt;;
#showme herblist;
#showme ;
#showme &lt;149&gt;==       &lt;229&gt;SCRIPTS&lt;149&gt;       ==&lt;088&gt;;
#showme &lt;149&gt;=========================&lt;088&gt;;
#showme combat;
#showme herbing;
#showme logging;
#CR}

#alias {herblist} {#showme ;
#showme &lt;229&gt;Spell Name&lt;088&gt;      - &lt;229&gt;Potion Name&lt;088&gt;   - &lt;229&gt;Ingredients&lt;088&gt;;
#showme &lt;149&gt;======================================================================&lt;088&gt;;
#showme cure-poison     - &lt;129&gt;green&lt;088&gt;         - parsley, rosemary, and sage.;
#showme remove-curse    - &lt;239&gt;brown&lt;088&gt;         - parsley, sage, and thyme.;
#showme refresh         - &lt;269&gt;effervescent&lt;088&gt;  - sage, rosemary, and thyme.;
#showme warmth          - &lt;159&gt;pink&lt;088&gt;          - parsley, fennel, and valerian.;
#showme stone-skin      - &lt;109&gt;light grey&lt;088&gt;    - rosemary, fennel, and vervain.;
#CR}</pre>

Firstly, we see the standard template being used followed by some color code comments. VT100 dictates how ANSI characters, including color, are to be sent and displayed. *Tin++ supports the VT100 control set and it implements them by a three digit code. Their manual [describes the codes](http://tintin.sourceforge.net/manual/colors.php "TinTin++ manual for color codes") and shows how to use them. The included comments are a simple reminder.

Next is an alias command called **thelp**. This serves as the internal help command for all custom scripts. It has to be manually updated, but when more than a handful exist, it is nice to have an in-game reference. The **showme** command prints messages locally on the client and does not transmit them to the server. This is used to show system messages. In this case, thelp prints a list of help commands and available scripts that can be toggled on or off. Each showme line ends with a semicolon so that a new line is created. **#CR** will print a carriage return so that text will line up correctly.

The color being used for the equal signs is 149. This will print the following text in bold (1), blue foreground (4), and the default background color (9). The color being used for &#8220;LISTS&#8221; is bright (2), green foreground (2), and the default background color (9).

The next alias is a truncated help menu showing in-game potions that can be brewed and the required herbs to make them. There are no new commands, but it seemed like a good idea to add more than one help alias. Recall at the beginning of this script that there was a script section showing &#8220;combat,&#8221; &#8220;herbing,&#8221; and &#8220;logging.&#8221; These are scripts that I keep separate with built in logic to toggle them. For example, if people start dying Gangs Of New York style, I don&#8217;t want to waste processing time on picking herbs. This allows for it to be quickly toggled off and the help entry reminds me of what the command is called.

This is just another way that aliases can be used beyond being glorified shortcuts. They do not add any advantage to players, but are handy reference guides. Hopefully this will give players new to scripting some ideas on things that they may not have thought of before.

**Previous:** [Part 2, Aliases](http://erikmusick.com/www-part-2-aliases/)

**Next:** [Part 4, Script Template](http://erikmusick.com/www-part-4-script-template/)
