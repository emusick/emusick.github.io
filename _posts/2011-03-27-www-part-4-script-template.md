---
id: 83
title: 'WWW &#8211; Part 4, Script Template'
date: 2011-03-27T00:36:28+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=83
permalink: /www-part-4-script-template/
categories:
  - Games
tags:
  - muds
  - script
---
The following is a base template to use for creating *Tin++ scripts. A class is created to contain all the appropriate actions, tickers, aliases, etc. Following that, an alias is created that allows the user to toggle the class on or off. Not only does this simply toggle states, but everything listed within the class will be removed when not in use. This removes unnecessary processing and memory bloat or any overloaded functions you may have implemented. The toggle alias will not be removed however so it can be toggled at any time.

<pre>#nop ###################################
#nop ## Script Name
#nop ## usage: 'on', 'off', ''
#nop ## default: 'on'
#nop ## toggle_var: 'Something'
#nop ###################################

#variable something on

#class {class_Something} {kill}
#class {class_Something} {open}

...
do stuff
...

#class {class_Something} {close}

#alias {something}
{
    #if {"%0" == "on"}
    {
        #if {"$something" != "on"}
        {
            #class {class_Something} {read} {config/scripts/something.tin};
            #showme &lt;159&gt;Something has been enabled!&lt;088&gt;;
            #CR
        }
        { #showme &lt;159&gt;You are already running Something.&lt;088&gt;;#CR }
    };
    #if {"%0" == "off"}
    {
        #if {"$something" == "on"}
        {
            #variable something off;
            #class {class_Something} {kill};
            #showme &lt;159&gt;Something has been disabled!&lt;088&gt;;
            #CR
        }
        { #showme &lt;159&gt;You are not running Something.&lt;088&gt;;#CR }
    };
    #if {"%0" != "off" && "%0" != "on"}
    { #showme &lt;159&gt;Turn Something on or off? ($something)&lt;088&gt;;#CR }
}</pre>

Hopefully this provides not only the foundation, but ideas for creating more complex logic within your favorite realm.

**Previous:** [Part 3, More Aliases](http://erikmusick.com/www-part-3-more-aliases/ "WWW – Part 3, More Aliases")
