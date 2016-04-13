---
id: 80
title: Hash, huh, what is good for?
date: 2011-03-12T22:54:49+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=80
permalink: /hash-huh-what-is-good-for/
categories:
  - Forensics
  - Philosophy
tags:
  - hash
  - validate
---
Hashes are good for something, but they are a bit misunderstood. This post will not delve into the mechanics of hash values; there are many sources available online that far exceed my knowledge and ability to express. Instead, this article will discuss why hash values were created in the first place.

Time and time again we hear about how hash values are for identifying known files. Or how they are being used to definitively state that a file has not changed. Neither of these concepts describe the purpose of hashes. They are by-products of the uniqueness of a hash, but are not intrinsic properties. Hash values have a single purpose, to validate the integrity of a data set. This is obviously different from identifying files, but its difference from state changes is subtle.

Firstly, identification of files. If hashes represent a specific set of data, then it lends itself quite well to the task of identifying other files that are wholly comprised of the base data set. However, stating that hashes are for identifying like files is incorrect. They check the integrity to ensure that no changes have occured to the original data set.

In examining a common scenario, we can see the subtlety in the second illusion of hashes. Forensic examiners almost always hash their original evidence media. What follows is the catch. The obtained hash value is **not** a representation of the media. It **is** a represntation of the obtained image. While one can reasonably state that the obtained hash value correlates to the original media, this is a mere guess.

This is more easily understood when working with dynamic environments such as imaging RAM or live hosts and networks. In this case, nearly everyone would agree that the hash is representative of the obtained image which itself is representative of a single snapshot in time (a &#8220;moment&#8221; for the physics people out there). For some reason, this understanding is lost when dealing with traditional media.

**TL;DR**

Hashes can only describe a data set. Stop abusing hashes and start understanding your choice of words.