---
id: 114
title: Topix Artifacts
date: 2011-10-08T16:02:10+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=114
permalink: /topix-artifacts/
categories:
  - Forensics
tags:
  - artifacts
  - web
---
Topix is a news site that revolves around community created forums. Some small towns and communities use this to connect with the public. For forensic examinations, Topix forums are standard web pages. This means piecing together paged information in unallocated space. The following are some specific searches that can be performed to target some activities.

### Author

The author of a post can be identified by searching for the following string where **username** is the specific user&#8217;s account name that is sought.

<pre>&lt;div class="authorsn"&gt;username&lt;/div&gt;</pre>

### Registered Users

When registered users post comments, additional information is present which can be found in the HTML pages. The value **username** has been substituted for the user&#8217;s account name being sought.

Link to user profile:

<pre>&lt;a t="post-usersntxt" href="member/profile/username"&gt;username&lt;/a&gt;</pre>

If an avatar is present:

<pre>&lt;a t="post-useravatar" href="/member/profile/username"&gt;</pre>

Date the user joined:

<pre>&lt;p class="regjoined" style="padding-top:7px; color:#333"&gt;</pre>

Geolocation information if enabled:

<pre>&lt;p class="geoip_isp"&gt;</pre>

### Logged In

If the user is logged in, a message may appear as the following where **username** is the user&#8217;s account that is sought:

<pre>You are currently logged in as &lt;span style="font-weight:bold"&gt;username&lt;/span&gt;</pre>

<pre>&lt;p&gt;Welcome, &lt;a t="hat-profile-link" href="/member/profile/username"&gt;username&lt;/a&gt;&lt;/p&gt;</pre>

### Posting Replies

The following example is from when a user attempts to create a reply to another&#8217;s comment. The string **username** is the user account making the reply. Some extraneous text has been replaced to consolidate the example.

<pre>&lt;form action="/forum/post" method="POST" id="forumEditForm"&gt;

&lt;input type="hidden" name="timestamp" value="1267635551"&gt;

&lt;input type="hidden" name="nonce" value="eV8KnGw2DY7pepxxJ3fL/A"&gt;

&lt;input type="hidden" name="replypostid" value=""&gt;

&lt;input type="hidden" name="quotepostid" value="22"&gt;

&lt;input type="hidden" name="submitted" value="1"&gt;

&lt;input type="hidden" name="warned" value=""&gt;

&lt;input name="forum" type="hidden" value="city/clarendon-ar"&gt;

&lt;input name="threadid" type="hidden" value="T9MU3NUTMQOOLSC8"&gt;

&lt;input name="nosubjectedit" type="hidden" value="1"&gt;

&lt;input name="subject" type="hidden" value="Why are people threatened by intelligence and success?"&gt;

...

You are currently logged in as &lt;span style="font-weight:bold"&gt;username&lt;/span&gt;.

...

&lt;tr&gt;

&lt;td rowspan="3"&gt;Comments&lt;/td&gt;

&lt;td&gt;&lt;textarea name="comments" rows="10" style="width: 90%"&gt;[QUOTE who="quoted_users_name"]I understand about the tax dollars, but do you also understand that if an emergency was to happen god forbid, would it not be wonderful if our Chief could respond in a timely manner from his home. And may I say that his home has been in Clarendon for the time he has been here until a few months ago because of the water situation. I am a citizen of Clarendon and I pay my taxes also, but I have seen a difference since Chief Smith took office. All I ask is give this man some time to find him a place to call home and bear with him until then.[/QUOTE]&lt;/textarea&gt;&lt;/td&gt;

&lt;/tr&gt;

...

Inappropriate posts may be removed by the moderator. &lt;a style="border-left:none; padding:0 2px 0 0" t="forum-post-feedback" href="#" onclick ="open_feedback('http://www.topix.net', { 'node' :'city/clarendon-ar' }); return false;" &gt;Send us your feedback&lt;/a&gt;.&lt;</pre>

For every comment or reply, there is a date given for the post. This is identified by **name=&#8221;timestamp&#8221;**. The timestamp is encoded as a Unix Numeric Value. In this case, the value 1267635551 equates to Wed, 03 March 2010 16:59:11 UTC.

If the comment is a reply, the **name=&#8221;quotepostid&#8221;** value will represent which post in that thread is being replied to. In this case, the 22nd post in the thread is being replied to.

The city and state forum to which it has been posted is identified by the **value=&#8221;city/** string. In this case, Clarendon Arkansas. The Topix site hosts a number of forums. The **name=&#8221;forum&#8221;**. This can be appended to the forum root path to obtain the main link for this forum. In this case, the full address would be _topix.com/forum/city/clarendon-ar/_.

The specific thread which was viewed is identified by the **name=&#8221;threadid&#8221;** value. When prefixed with a **T** (possibly to indicate &#8220;thread&#8221;), the value can be appended to the forum name to directly access the specific topic. In this case, the topic would be located at _topix.com/forum/city/clarendon-ar/TT9MU3NUTMQOOLSC8_. If the topic link is followed by a **/p** and a number, that is to indicate the page number. For instance, _topix.com/forum/city/clarendon-ar/TT9MU3NUTMQOOLSC8/p2_ would mean that the second page of the topic T9MU3NUTMQOOLSC8 was being viewed.