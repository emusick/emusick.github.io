---
id: 29
title: Worlds Within Worlds
date: 2010-12-01T10:06:30+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=29
permalink: /worlds-within-worlds/
categories:
  - Games
tags:
  - muds
  - script
---
I enjoy games. I also enjoy &#8220;enhancing&#8221; my game experience by customizing. The only thing that really holds me back from over-enhancing is memory consumption and overall efficiency. I found out that [MUDs](http://en.wikipedia.org/wiki/MUD "Description of what MUDs are") are not only enjoyable, but highly customizable based on the client one uses. Since they are pure text environments, it means there is a lot of flexibility when it comes to &#8220;extra&#8221; resources.

In particular, I am quite fond of [Underworld Dreams](http://dreams.daestroke.com/ "Homepage for Underworld Dreams"). It probably has to do with it being my first real online game (aside from Quake 3 Arena), where I learned to type, and the meeting of a few friends. Now, one can play MUDs with any old telnet client. However, one will get paging issues, scroll spam, no shortcut to typing, and general frustration. Luckily there exists specialized clients for MUDing which are telnet clients on steroids. [TinTin++](http://tintin.sourceforge.net/index.php "Homepage for TinTIn++") (and its Windows port WinTin++) is my favorite; although, [zMud](http://www.zuggsoft.com/zmud/zmudinfo.htm "Homepage for zMud") and [gMud](http://sourceforge.net/projects/g-mud/ "Homepage for gMud") are both really popular among others.

WinTin++ has one major short-coming and that is that it runs on Windows. There is no shell access in Windows and this limits the amount of insane scripting that is possible. TinTin++ on the other hand works in Linux and has full system access which allows the executing of any external applications. This makes TinTin++ much more exciting. That said, the syntax between the two clients is the same minus some feature restrictions. This means that scripts are portable across platforms. And for the really ambitious, WinTin++ can be copied to external devices after installation so that MUDing from work is convenient.

After installing *Tin++ and running it, you are left with a blank, black screen. **Sessions** must be started each time in order to make outbound connections. For Underworld Dreams, one could enter _session {UD} {66.93.4.184} {3000}_ every time or add it to a default script. Since scripting is the whole point of the article (minus the introduction to MUDs), let us begin. Assuming we will be adding lots of enhancements, we will add in some structure to begin with. Particularly, we will wrap our default script in a default **class** which allows for better cascading. The result of this is, we define a default group that has all of our default settings in it. Then we will later override some of these with character specific needs. We will also enable logging all input and output to a plain text file. Here is an example:

<pre>#CLASS {cl_default} {kill}
#CLASS {cl_default} {open}

#SESSION {UD} {66.93.4.184} {3000}

#CONFIG log plain
#FORMAT {time} &#123;%T}
#FORMAT {logfile} {logs/ud_%Y%M%D.txt} {$time $time $time};
#LOG append $logfile;

#read {config/default/actions.tin}
#read {config/default/aliases.tin}

#class {cl_default} {close}</pre>

The **class** functions serve to clear out all remnants from a previous session, open a new one, and add everything to it before closing. The **session** command connects to the Underworld Dreams (affectionately known as UD) server. The **read** commands will be additional commands and functions that are injected into our default class. **Aliases** are essentially shortcuts and **actions** are automated tasks based on certain input. The log portion enables logging as plain text, formats the file name, and stores them in a &#8220;log&#8221; directory in the same location as the *Tin++ executeable.

Before launching \*Tin++, create the &#8220;log&#8221; and &#8220;config&#8221; directories. Then place the above script into the config directory. I call mine &#8220;ud.tin&#8221; to signify that I am connecting to UD and that it is a \*Tin++ script. Now it is time to launch. At the scary blank, black screen enter _#read config/ud.tin_ and enjoy. In future posts, I will flesh out some more scripts I use including the aliases.tin and actions.tin mentioned above.

For more MUD options, visit [The MUD Connector](http://www.mudconnect.com/ "Homepage for MUD Connector"). They have server listings, forums, links to clients, and more.

**Next:** [Part 2, Aliases](http://erikmusick.com/www-part-2-aliases.html "Worlds Within Worlds - Part 2, Aliases")
