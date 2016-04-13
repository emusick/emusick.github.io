---
id: 26
title: Facebook Artifacts
date: 2010-12-01T12:33:14+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=26
permalink: /facebook-artifacts/
categories:
  - Forensics
tags:
  - internet
---
All internet browsing leaves remnants lying around the system simply waiting to be plucked. The problem is, finding relevant data and, hopefully, quickly. In the case of Facebook, quickly is not always feasible due to the sheer amount of data that is transferred and consequently paged out. The below items may help in targetting specific activities. None of the strings are hard fast, but may be useful in targeting data located within unallocated space.

**User Logged In**

When attempting to determine whether a user was logged in, the title bar in the browser will be different for those logged in and those who are not. This does not tell you who was logged in, but merely that someone was. When a user is not logged in, the format is &#8220;**Username | Facebook**&#8220;. However, these two are swapped when a user logs in; thus becoming &#8220;**Facebook | Username**&#8220;. This can be identified in the HTML and in possible screenshots.

<div style="width: 386px" class="wp-caption alignnone">
  <img title="Anonymous login on Facebook" src="/content/img/Facebook_anonymous.png" alt="Anonymous login on Facebook" width="376" height="125" />
  
  <p class="wp-caption-text">
    Anonymous login on Facebook
  </p>
</div>

&nbsp;

<div style="width: 385px" class="wp-caption alignnone">
  <img title="Facebook account logged into" src="/content/img/Facebook_logged_in.png" alt="Facebook account logged into" width="375" height="86" />
  
  <p class="wp-caption-text">
    Facebook account logged into
  </p>
</div>

**Current User**

It may be possible to find the currently logged in user&#8217;s profile ID by finding the string below where **#** is the profile ID.

<pre>href=\\\"http:\\\/\\\/www.facebook.com\\\/profile.php?id=#\\\"&gt;You</pre>

<pre>\"c_user\":\"#\"</pre>

The email address associated with the user&#8217;s account may be found using the following string where **email** is the user&#8217;s email.

<pre>\"lxe\":\"email\"</pre>

**Account Modification**

While useful in finding the currently logged in user&#8217;s name, the following is more noteworthy when it comes to identity theft.

<pre>div id="change_all_names_val"&gt;</pre>

<pre>id="old_full_name"</pre>

The account settings page is also home to the password reset option. The following will help identify whether the account settings page was visited and possibly help corroborate whether the account had been hijacked.

<pre>class="password_confirm_password"&gt;</pre>

<pre>Password change not successful"</pre>

**Personal Messages**

Personal messages (&#8220;private messages&#8221; or, simply, PMs) may be identified as well. They are stored much like email in an inbox fashion. The sender&#8217;s name and a partial subject line are present. The following can help narrow down searches for PMs.

<pre>a href=\"http:\/\/www.facebook.com\/?sk=messages&tid=</pre>