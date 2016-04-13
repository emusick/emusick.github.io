---
id: 104
title: 'Lawyers &#038; Testimony &#8211; Types of File States'
date: 2011-08-05T09:03:57+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=104
permalink: /lawyers-testimony-types-of-file-states/
categories:
  - Forensics
tags:
  - lawyers
---
During the course of a forensic examination, a number of files are usually presented as evidence along with a report. One can peruse the files at their own leisure and life is good. Then comes the report and lots of jargon. Particularly, the term &#8220;unallocated&#8221; shows up and generally sounds mysterious. Its mystery is job security, but the concept is easy to understand. When talking about files there are three states: allocated, deleted, and unallocated &#8212; I suspect &#8220;states&#8221; may be debatable, but it will work for the purpose of this article.

Allocated files are easy. These are the files you see when you browse around on your computer. They can be clicked on and the associated application opens. Movies are watched. Songs are heard. Documents are read. It is like watching Bob Ross paint &#8230; peaceful. The file&#8217;s owner, created and modified date, file name, and more are recorded and visible to the user. They are called allocated because space has been reserved to hold the contents of this file. If it is allocated, no other file may reside in that space.

Deleted files are also fairly easy. For the most part, these are the files located in the Recycle or Trash bin. The actual term for this purgatory state depends on the file system. A file system is essentially a large card catalog system (when was the last time you heard that?) or index that keeps track of all the file allocations. Deleted files are still allocated, but they have been moved to a different location and they lose some information about them. After a file is deleted, it no longer appears in that location. The file system has moved it to a different structure that is not completely transparent to the user. However, forensic practitioners can retrieve these files and still provide a good deal of information about them. Typically, the original file name and location (file path) can be found along with when the file was deleted.

Unallocated files are a bit tricky in practice, but they are an easy concept. Files are not really unallocated, but the previously reserved storage area is marked as being available to store new files. This occurs, generally, after a user purges or empties their Recycle Bin or Trash. The original content is not harmed in any way. The index controlled by the file system is modified and the entry listing all of the file information is removed (not exactly true as it depends on the file system). Forensic practitioners can search the entirety of the unallocated space (space not belonging to allocated files) looking for lost files. Since the index entry for the file is removed, the file name, file path, dates and times, file owner, etc. is all lost. This information can not be retrieved; although, some files may include parts of this information internally by their very nature and will be retrieved as part of the file contents.

The process of retrieving files from unallocated space requires a bit of effort. One thing to note is that files are not stored as a single entity. They are sliced into a specifically sized blocks and those blocks are written. To make matters worse, not all blocks are stored together. This can make the retrieval process tedious if not impossible. This also helps to explain why, particularly in the case of pictures and movies, they stop part way through. Either the necessary blocks were stored elsewhere or they were overwritten by a different file. In some cases, especially with movie files, the video may switch movies. This is typically due to two video blocks being stored adjacently and the tool or practitioner being unable to distinguish between the two at such a low level.

**TL;DR**

Think of files as chapters in a book. Allocated files are just like a pristine book. Browse the table of contents, find something interesting, and jump to the chapter. Deleted files are on par with having the chapter name removed from the table of contents. The page number and length are known. If a reader goes to that page number, the chapter is still visible at the beginning of the chapter (no substantial change to the file or information about it). Unallocated files are like having the table of contents entry blanked out. No information can be found about the chapter, but you can still find it by flipping through each and every page. Once a chapter is found, the file contents are (for this article) unchanged.