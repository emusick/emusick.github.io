---
id: 48
title: Forensic Software Validations
date: 2010-12-31T19:55:30+00:00
author: Erik Musick
layout: post
guid: http://erikmusick.com/?p=48
permalink: /forensic-software-validations/
categories:
  - Forensics
tags:
  - validate
---
2016-04-13 Update: Removed links to validation documention. They will be uploaded to a repo later.

I hear that we should validate our software to the point it makes me nauseous. &#8220;I validated it, but I didn&#8217;t write it down&#8221; is a close runner up for calling in sick (hint: if you did not document it, you did not validate it). What really irks me though is how difficult it is to find examples on how to validate software, hardware, and methodologies. Paraben is the only training (out of 14) I have been to in the last year that provided any material of substance on validating. To take the documenting process a step further, I decided I would publish what little I have along with some source files to try and help others who find themselves similarly frustrated. I know there must exist better, more effective styles, but what follows is what I have pieced together myself. Hopefully someone has enhancements or their own work that they are willing to share.

One of the first validations I wrote was for Tableau&#8217;s TIM application. Yes, it may look weird, but I really like [LaTeX](http://www.latex-project.org/ "Homepage for LaTeX, a typesetting application"). The only thing I changed to release it was substituting &#8220;Company Name&#8221; for the actual company (pardon any errors, this is provided as-is). In case someone would like to use this as a template, I have uploaded the source latex files which produced that document: [tableau_tim.tex](/content/docs/tableau_tim.tex "My LaTeX source file for the Tableau Imager validation") and title.tex. If that does not terrify you and you are interested in using LaTeX, I highly recommend the [portable version of MiKTeX](http://miktex.org/portable/about "Homepage for MiKTeX portable, a compilation of LaTeX"). There is an installable version as well and if you are running Linux, pulling in the graphical front-end [Lyk](http://www.lyx.org/ "Homepage for Lyx, a graphical interface to LaTeX") should pull in all of the underlying dependencies.

Here is another example of an older version of VirtualBox. The source LaTeX file for the content is virtualbox.tex. A final example is for Raptor version 2.0 which is a bit more complex. The source LaTeX file for the content is raptor.tex.

Hopefully, this helps someone who has been looking for a way to construct a validation. For more validations that I have written, please see the Scribd collection I have created for Validations. If anyone has suggestions or examples, I would greatly appreciate seeing them.

**TL;DR**

If you did not document it, you did not validate it. See the Validations collection.
