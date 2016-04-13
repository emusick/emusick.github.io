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
I hear that we should validate our software to the point it makes me nauseous. &#8220;I validated it, but I didn&#8217;t write it down&#8221; is a close runner up for calling in sick (hint: if you did not document it, you did not validate it). What really irks me though is how difficult it is to find examples on how to validate software, hardware, and methodologies. Paraben is the only training (out of 14) I have been to in the last year that provided any material of substance on validating. To take the documenting process a step further, I decided I would publish what little I have along with some source files to try and help others who find themselves similarly frustrated. I know there must exist better, more effective styles, but what follows is what I have pieced together myself. Hopefully someone has enhancements or their own work that they are willing to share.

One of the first validations I wrote was for [Tableau&#8217;s TIM](http://www.scribd.com/doc/46122749/Validation-Tim-1-11?in_collection=2784627 "Validation for Tableau's TIM software I wrote") application. Yes, it may look weird, but I really like [LaTeX](http://www.latex-project.org/ "Homepage for LaTeX, a typesetting application"). The only thing I changed to release it was substituting &#8220;Company Name&#8221; for the actual company (pardon any errors, this is provided as-is). In case someone would like to use this as a template, I have uploaded the source latex files which produced that document: [tableau_tim.tex](/content/docs/tableau_tim.tex "My LaTeX source file for the Tableau Imager validation") and [title.tex](http://erikmusick.com/content/docs/title.tex "My LaTeX source file for the title page used in all my validations"). If that does not terrify you and you are interested in using LaTeX, I highly recommend the [portable version of MiKTeX](http://miktex.org/portable/about "Homepage for MiKTeX portable, a compilation of LaTeX"). There is an installable version as well and if you are running Linux, pulling in the graphical front-end [Lyk](http://www.lyx.org/ "Homepage for Lyx, a graphical interface to LaTeX") should pull in all of the underlying dependencies.

Here is another example of an older version of [VirtualBox](http://www.scribd.com/doc/46122743/Validation-Virtual-Box-3-2-0?in_collection=2784627 "My validation of VirtualBox version 3.2.0"). The source LaTeX file for the content is [virtualbox.tex](/content/docs/virtualbox.tex "My source LaTeX file for the VirtualBox 3.2.0 validation"). A final example is for [Raptor version 2.0](http://www.scribd.com/doc/46122753/Validation-Raptor-2-0?in_collection=2784627 "My validation for Raptor LiveCD") which is a bit more complex. The source LaTeX file for the content is [raptor.tex](/content/docs/raptor.tex "My source LaTeX file for the Raptor LiveCD validation").

Hopefully, this helps someone who has been looking for a way to construct a validation. For more validations that I have written, please see the [Scribd collection](http://www.scribd.com/document_collections/2784627 "My Scribd collection for all validations that I have written") I have created for Validations. If anyone has suggestions or examples, I would greatly appreciate seeing them.

**TL;DR**

If you did not document it, you did not validate it. See the [Validations collection](http://www.scribd.com/document_collections/2784627 "My Scribd collection for all validations that I have written") for examples. Additional [Best Practices](http://www.scribd.com/my_document_collections/2784650 "My Scribd collection for all best practices that I have written"), [Guides](http://www.scribd.com/my_document_collections/2784658 "My Scribd collection for all guides that I have written"), and [Forms](http://www.scribd.com/my_document_collections/2784665 "My Scribd collection for all forms that I have written") have been posted as well.