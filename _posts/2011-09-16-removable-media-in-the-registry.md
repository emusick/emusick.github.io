---
id: 108
title: Removable Media in the Registry
date: 2011-09-16T13:06:26+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=108
permalink: /removable-media-in-the-registry/
categories:
  - Forensics
tags:
  - 7
  - registry
  - usb
  - vista
  - windows
---
What follows are some rough notes taken during AccessData&#8217;s Vista class. Although much of it has been discussed in many trainings, the portion about EMDMgmt and MountPoints2 was completely new to me. Many thanks to Dustin Hurlbut for his great class.

**HKLM/System/MountedDevices**
  
Shows devices attached to the system
  
GUIDs and vendor information can be identified
  
Last volume letter an attached drive was mounted to

**HKLM/System/CurrentControlSet#/Control/USBStor**
  
Shows Device ID

* In Windows XP, a parent ID prefix is found instead of a Vendor ID

**HKLM/System/CurrentControlSet#/Control/DeviceClasses**
  
Shows device information by GUID
  
Last Written updates when device is attached or booted with device attached

**HKCU/Software/Microsoft/Windows/CurrentVersion/Explorer/MountPoints2**
  
Entries correspond to GUIDs found in MountedDevices
  
Last Written updates when device is attached or booted with device attached
  
Used to determine which user has attached the device
  
May be more accurate than DeviceClasses

**HKLM/Software/Microsoft/Windows Portable Devices/Devices**
  
Detailed device information
  
Multiple entries for the same device if volume name changed
  
Historical tracking of volume name changes

**HKLM/Software/Microsoft/Windows NT/CurrentVersion/EMDMgmt**
  
Stores test results for Ready Boot compatibility
  
Tests are not automatically run when device is attached
  
DeviceStatus value of 2 equates to a pass; all other values are fail

**Determine the first time a device was attached:**
  
Investigate %WINDIR%/inf/setupapi.dev.log

**Obtain Vendor ID from Windows:**

  1. Run diskmgmt.msc
  2. Right-click on any volume name
  3. Select Properties
  4. Click the Hardware tab
  5. Select desired device
  6. Click the Properties button
  7. Click the Details tab
  8. Select the Device Instance Path property dropdown

* Note, in Windows XP, a &#8220;parent ID prefix&#8221; is generated for MountedDevices

**Obtain persistent volume GUIDs:**
  
Follow the same steps for Vendor ID, but select Device Class GUID from dropdown