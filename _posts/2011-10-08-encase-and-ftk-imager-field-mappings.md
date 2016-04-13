---
id: 120
title: EnCase and FTK Imager Field Mappings
date: 2011-10-08T16:42:42+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=120
permalink: /encase-and-ftk-imager-field-mappings/
categories:
  - Forensics
tags:
  - encase
  - ftk
  - imaging
---
About a year ago, we began using tools outside of EnCase to perform imaging. This caused some initial confusion when importing evidence into EnCase and certain expected fields were no longer filled in. The following was written to compare which case fields were common between EnCase (version 6.17 I believe) and FTK Imager (2.9). The following is a mapping of fields.

<table>
  <tr>
    <th>
      FTK Field
    </th>
    
    <th>
      EnCase Field
    </th>
  </tr>
  
  <tr>
    <td>
      Case Number
    </td>
    
    <td>
      n/a
    </td>
  </tr>
  
  <tr>
    <td>
      Unique Description
    </td>
    
    <td>
      Evidence Name
    </td>
  </tr>
  
  <tr>
    <td>
      Evidence Number
    </td>
    
    <td>
      Evidence Number
    </td>
  </tr>
  
  <tr>
    <td>
      Examiner
    </td>
    
    <td>
      n/a
    </td>
  </tr>
  
  <tr>
    <td>
      Notes
    </td>
    
    <td>
      Notes
    </td>
  </tr>
</table>

Although we now primarily use Tableau&#8217;s Imager (TIM) and Guymager, any time we do use FTK Imager we will place the case number and suspect&#8217;s name in the notes section. This gives us some added flexibility in passing along information depending on who is processing and what application they are using. Of course, the imaging log file is present, but knowing not to rely exclusively on field names was a learning lesson. This has not been tested with EnCase version 7.