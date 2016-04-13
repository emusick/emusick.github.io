---
id: 35
title: Wiping Artifacts
date: 2010-12-07T17:51:45+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=35
permalink: /wiping-artifacts/
categories:
  - Forensics
  - Security
tags:
  - artifacts
---
In the middle of eating dinner after reading [A Quick Note About Shred](http://computer-forensics.sans.org/blog/2010/12/07/digital-forensics-quick-note-shred "SANS article link to A Quick Note About Shred"), there was an interesting artifact I recalled running across lately. The tool Eraser was used to wipe free space on a hard drive. It was also run as the user and not as administrator. This produced a log file at _%APPDATA%\Eraser 6\Task List.ersx._ It contained a list of every file that it was not able to wipe and since it was run as a user, there were many (due to permissions and file locks for open files). This included Prefetch and temporary files that had been deleted after the wipe and prior to the seizure.

Two lessons can be taken from this. One is, logs are invaluable if you can find them. Two is, if you want something done properly, do it as root.