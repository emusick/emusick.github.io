---
id: 31
title: 'WWW &#8211; Part 2, Aliases'
date: 2010-12-04T13:39:49+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=31
permalink: /www-part-2-aliases/
categories:
  - Games
tags:
  - muds
  - script
---
Continuing from [Part 1](http://erikmusick.com/worlds-within-worlds/), this section will discuss [Aliases](http://tintin.sourceforge.net/manual/alias.php "TinTin++ manual page for aliases"). Aliases are shortcuts to abbreviate commands. Below is an example of some default aliases, with headings for easier reading. Notice that the headings are set of with **nop** which is programming lingo for &#8220;No Operation&#8221; or, more simply, &#8220;do nothing.&#8221; It is based off the default script created in part where we set up a default class template.

<pre>#class {cl_aliases} {kill}
#class {cl_aliases} {open}

#nop ###################################
#nop ## Aliases
#nop ###################################

#nop -=-=-=-=-=-=-= Class =-=-=-=-=-=-=-
#ALIAS {antipal}    {#read config/class/antipal.tin}
#ALIAS {mage}       {#read config/class/mage.tin}
#ALIAS {quessite}   {#read config/class/quessite.tin}
#ALIAS {warlock}    {#read config/class/warlock.tin}

#nop -=-=-=-=-=-=-= Quest =-=-=-=-=-=-=-
#ALIAS {qr} {quest request}
#ALIAS {qc} {quest complete}
#ALIAS {qi} {quest info}
#ALIAS {ql} {quest list}
#ALIAS {qs} {quest stats}

#nop -=-=-=-=-=-=-=  Env  =-=-=-=-=-=-=-
#ALIAS {ps} {portal set %1}
#ALIAS {ep} {enter portal}
#ALIAS {ud} {unlock %0; open %0}

#ALIAS {ec} {look in corpse}
#ALIAS {li} {look in %0}
#ALIAS {scc} {sac all.corpse}
#ALIAS {trash} {drop all.%1; sac all.%1}

#class {cl_aliases} {close}</pre>

Breaking this down, there are three main sections of default aliases: classes, quests, and environment. The class section is in anticipation of adding subsequent configuration files for class specific functions. We will see an example of those a little later once more of the *Tin features have been explained. The quest section has a naming convention that models the original commands. These aliases are merely abbreviations for commonly used commands. Typing _qs_ will actually send _quest status_ to the game.

The environment section is a little different. There are some abbreviated commands such as **ep** and **ud**; however, there are some that contain a list of commands. In *Tin++, input variables can be used to separate input values. For instance, take the **trash** command. If one were to enter _trash sword_ every sword in your inventory would be dropped and subsequently deleted (or, sacrificed in UD lingua). The two commands are separated by the semicolon and the value &#8220;sword&#8221; is substituted in place of the _%1_. Let us say for instance that the command given was _trash golden rod_. In this case, every &#8220;golden&#8221; item would be dropped and sacrificed. This may not be the intended goal. One could therefore modify the alias to _drop all.%1 %2; sac all.%1 %2_ or simply use the _%0_ variable which lumps all arguments into one variable. Then, all &#8220;golden rod&#8221; would be dropped and sacrificed.

Let&#8217;s look at adding some logic to these basic aliases. Create a new section for other, miscellaneous aliases. We will play the role of a lover, not a fighter. Except when we see AnnoyingPlayer since they are, well, annoying.

<pre>#ALIAS {lover} { #if {"%0" == "AnnoyingPlayer"} {kill %0} {hug %0}}</pre>

This checks to see if your target is &#8220;AnnoyingPlayer.&#8221; If it is, you will attack them. Otherwise, you will give the player a hug. There are many, many different uses of aliases. TinTin++ has a great [manual](http://tintin.sourceforge.net/manual/ "TinTin++ manual") and a useful [forum](http://tintin.sourceforge.net/board/ "TinTin++ forums") as well.

**Previous:** [Part 1, Introduction](http://erikmusick.com/worlds-within-worlds/)

**Next:** [Part 3, More Aliases](http://erikmusick.com/www-part-3-more-aliases/)
