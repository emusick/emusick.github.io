---
id: 41
title: Lookout Mobile Security App
date: 2010-12-23T00:12:10+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=41
permalink: /lookout-mobile-security-app/
categories:
  - Mobile
  - Security
---
I recently ran across a [flutter of tweets](http://twitter.com/Lookout "Lookout Twitter account") mentioning [Lookout](https://www.mylookout.com/ "Lookout homepage") and decided to try it out today. The software works on Android, Blackberry, and iPhone OSes. Aside from the standard &#8220;where&#8217;s my phone&#8221; and remote wiping <a title="Lookout features page" href="https://www.mylookout.com/features/security" target="_blank">features</a>, it apparently scans installed applications to determine what data they have access to. It does not allow one can restrict access, but merely report on data access controls. The software also comes with anti-spyware scanning. They do have free and <a title="Lookout premium information and comparison page" href="https://www.mylookout.com/premium/" target="_blank">premium</a> versions ($3 per month or $30 per year).

Installing requires access to most everything on your phone. This isn&#8217;t too surprising, but a little disconcerting to read through. I did not enable backups and will not until I find out where and how they are stored. Plus, I don&#8217;t care for lots of automated tasks running or battery drains. It does come with a 30 day free Premium trial. I accepted the trial, but removed all backup (call history and pictures) options leaving only the Privacy Advisor selected.

The initial screen is nice and easy to read. Scanning for malware was fairly quick (less than a minute), but will depend on how many apps you have installed. In my case, it claims to have scanned &#8220;189 applications,&#8221; but I know I&#8217;ve only installed maybe a dozen apps. Most of those are internal apps or app components, I suspect.

The Privacy Advisor, which is part of the premium version, is quite nice. According to it, of the 189 applications 11 can locate me, 14 can read identity information (phone ID which is unchanging and unique to you &#8230; often used to send targeted advertising), and 1 can access messages. Clicking on the Dashboard breaks the applications down by category (tracking, ID, and messages). Of course the single app accessing messages is Lookout (told you it required access to everything). Under &#8220;identity&#8221; there were the usual suspects (Amazon, Facebook, Gmail, etc), but a few odd ones including Pandora and TipCalc. The latter two show up due to in-app advertising. For tracking, everything appeared normal expect NFS Shift which is a built-in Need For Speed racing game. Why it needs to know GPS, I&#8217;m not sure. Interesting and useful, but nothing all that new. Since I am not aware of any spyware, I have no way of knowing whether it did an adequate scan.

The web interface is nice as well. It includes a fake picture of your phone model (a Droid-X in my case) along with your phone number (accessing phone ID data).  The Dashboard gives an overview of what features you have enabled. The Security tab shows when last scans were run and, presumably, if anything was found of interest. The Backup tab allows one to schedule backups and restore from previous backups. Three categories exist for pictures, calls, and contacts. It looks as though you can pick which category to backup and, possibly, specific photos or entries.

The missing device section is the expected embedded Google maps. The free version allows you to locate the map and cause the phone to scream even when muted. The premium version allows for remote locking and wiping. When locking the phone remotely, here is the warning that is given:

<div>
  <ul>
    <li>
      A message will be sent to your device. The screen will lock, preventing all use of the phone except for emergency calls.
    </li>
    <li>
      This may take a few minutes, and will only work if the phone is on and has a network connection.
    </li>
    <li>
      If your device is off now, but is later turned on, the lock will activate when it connects to the network.
    </li>
    <li>
      Unlock the device by visiting this page and clicking &#8220;Unlock&#8221;.
    </li>
  </ul>
</div>

Spamming the home key will show the desktop and the taskbar is always visible. Unlocking the phone remotely removes the &#8220;Lookout Lock Screen&#8221; dropping you back to the home desktop. I ran Pandora which runs in the taskbar in an attempt to bypass the lock. This did not work, but I did inadvertently get to a &#8220;Recently Performed&#8221; page which I&#8217;ve never seen. From this, I could run applications, but they were blocked by the &#8220;Lookout Lock Screen.&#8221; When I released the lock, I was sitting at a voice command menu. It may have be possible to start a voice command menu and bypass the lock that way, but I was not successful in doing so.

Here is the warning message for the scream function:

<div>
  <ul>
    <li>
      Make your device emit a loud siren for 60 seconds. (Caution: it&#8217;s very loud)
    </li>
    <li>
      Turn down volume or switch off device to stop the screaming.
    </li>
    <li>
      Network connection required; may take a few minutes.
    </li>
  </ul>
</div>

This causes the device to wail and vibrate. Attempting to mute or change volume while the device does not work. After entering your PIN/Pattern Lock, you can deactivate the siren from the &#8220;Lookout Lock Screen.&#8221; The web interface records when the last scream took place.

Under the Settings tab, one can modify the features. For missing device, there is &#8220;Notify me by email when my phone is located&#8221; and &#8220;Save each location my phone sends. (Unchecking will delete location history.)&#8221; You can also disable Lookout remotely which is a security issue in and of itself. Making sure no one has access to you Lookout account information should be obvious, but is many times overlooked by the use of weak passwords or checking online from insecure locations.

Make sure to check your account settings on the web interface, not just the phone settings. Otherwise you will miss the opportunity to disable email announcements, change the frequency of security updates, and change your time zone which is Pacific by default. One would think with full access to the phone that they could set the correct time zone, but alas. The security updates is a weekly email (by default) that enumerates the activity history of Lookout for the device; number of scans, found malware, any remote features used, etc.

All in all, it seems quite nice. Almost tempting to pay a premium account. For corporations, this would be a great thing. It would be nice if corporations simply paid the monthly/yearly fees for their users instead of having access to all their private data, but this may be too much of a hope for company paid-for phones. Although, not all phones are company owned, but they are expected to be used for company communication.

Continuing on the idea of corporations using this, but allowing their employees to maintain control of the software &#8230; the security update email would be a nice way for the employer to have a security check and not be in control. It would be a round about solution as Lookout does not support emailing this update to a secondary address, but a server side email policy that reroutes that message would not be difficult to implement.