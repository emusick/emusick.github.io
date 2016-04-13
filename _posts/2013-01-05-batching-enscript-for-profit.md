---
id: 257
title: Batching ENScript for Profit
date: 2013-01-05T21:29:44+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=257
permalink: /batching-enscript-for-profit/
categories:
  - Productivity
  - Programming
tags:
  - batch
  - evernote
  - script
  - windows
---
I found myself needing to import a lot of saved articles into Evernote. The ideal method would have been to use the built-in &#8220;Import Folder&#8221; process. Unfortunately, the articles I wanted to bring in were multipart with each section in a separate file and each article&#8217;s volume name was inconsistent. I also wanted to write a loader for ENScript which had the added benefit of giving some more control over the note naming.

The article volumes are stored in individual directories that contain all parts of the volume. The Windows batch file loader uses ENScript to import each part into an Evernote note, in a specific notebook, using a title structure of &#8220;Article VolumeNumber &#8211; PartNumber&#8221;. Content can not be appended to existing notes or this would be a moot exercise. After importing the volume parts, the notes can be merged within Evernote to create a single note containing the full article. Some loader intelligence exists so that single digit volume numbers and volume part numbers are padded with a zero to make everything look nice and to maintain proper sequencing within Evernote for merging. The first part of a volume is missing the volume part number in the title. If it were included, after merging the resulting note would still contain &#8221; &#8211; PartNumber&#8221; in the title. This means that no renaming is required after merging.

The loader itself can be tossed into a loop to iterate over a large number of directories containing volumes. The script is fairly straightforward and includes comments. It isn&#8217;t overly smart and not very elegant; it was meant to get work done. Windows batch files aren&#8217;t the place one wishes to spend much time anyway. I cleaned it up some and moved everything to variables at the top so that it would be easier for others to adopt. The only odd element is the rename line which appends a TXT file extension to everything in the directory. This is to ensure that Evernote loads the content of the files into notes instead of attaching them as files. Enjoy.

**Raw Code:**

<pre>:: ENImport.bat
:: Purpose:
::   Evernote Import
::   Utilizes ENScript to add fragmented file contents to new notes.
::
:: Author: Erik Musick
:: Documentation:
::   http://dev.evernote.com/documentation/local/chapters/Windows.php
:: Usage: ENImport.bat &lt;folder>

@ECHO OFF

:: Variables
:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

:: ENScript directory path
set ENPATH=D:\Evernote

:: Evernote notebook name
set ENNOTEBOOK=Notebook

:: Evernote title
set ENTITLE=Article

:: Set directory from provided user input
set FOLDER=%1

:: Set counter which represents volume numbers
set /a COUNTER=1

:: Keeps %COUNTER% from expanding instantly within the ENScript command
setlocal ENABLEDELAYEDEXPANSION

:: Uncomment to append a TXT file extension so that Evernote includes file content
ren %1\* *.txt

:: Set padding for single digit volume numbers (based on %FOLDER%)
set PAD=
if %FOLDER% lss 10 (set PAD=0)

for /F "delims=" %%f in ('dir /B/D %FOLDER%') do (
  :: If it isn't and less than 10, pad the single digit with a 0
  if !COUNTER! lss 10 (
  if !COUNTER!==1 (
    :: If this is the first part, do not create note with volume information to save renaming after merge
    "%ENPATH%"\ENScript.exe createNote /n "%ENNOTEBOOK%" /i "%ENTITLE% %PAD%%FOLDER%" /s "%1\%%f"
  ) else (
    "%ENPATH%"\ENScript.exe createNote /n "%ENNOTEBOOK%" /i "%ENTITLE% %PAD%%FOLDER% - 0!COUNTER!" /s "%1\%%f"
  )
  ) else (
  :: If it's greater than 9, no padding is necessary
  "%ENPATH%"\ENScript.exe createNote /n "%ENNOTEBOOK%" /i "%ENTITLE% %PAD%%FOLDER% - !COUNTER!" /s "%1\%%f"
  )
  
  :: Increment the counter (article part)
  set /a COUNTER=COUNTER+1
)

echo Finished importing %1
</pre>