---

layout: post
title: XAMPP Basics
author: pulkit
tags: [xampp, beginner, novice]

---

XAMPP is a great package to have for complete newbies in order to learn PHP-based website development. In one simple installation you can lay down the Apache Web Server, MySQL, PHP, Perl, phpMyAdmin etc. (an impressive list).

This blog, more than anything, is a narration of how one developer went and wrapped his head around what all XAMPP has to offer. If this helps you "ramp-up" as well ... then great!

1. What's a good place to install XAMPP?
	> As a rule of thumb, always choose a path without spaces and keep it short and simple, for example: `C:\apps\xampp\` would be a good location.
2. After an install what should my directory structure look like for easy access?
	> Trust me on this, you never ever want a structure such as `C:\apps\xampp\xampp\` ... why you ask? Because it annoys me!

	> In my opinion, the following default layout of XAMPP is ideal:
	```
	C:\apps\xampp\apache
	C:\apps\xampp\phpMyAdmin
	```
3. I know that Apache (part of the XAMPP bundle) uses the `httpd.conf` file to control what's hosted and what isn't. Then why can I not find any mention of apps such as phpMyAdmin in this file? Even though I can clearly see them hosted at locations such as `http://localhost/phpmyadmin/` etc.?
	> Technology or at least technology done well ... is all about making your product/components intuitive. A closer look at the `httpd.conf` file reveals some interesting information:
	```
	# XAMPP specific settings
	Include conf/extra/httpd-xampp.conf
	```
	> It becomes clearer that not all the information needs to be seated in the `httpd.conf` file, rather there are other files that have been laid down as part of the XAMPP installation which contain useful configuration information. In this case, we find that a file named `httpd-xampp.conf` has what we are looking for.
1. What's a good place to start tinkering?
	> Well I found the following [article](http://dalibor.dvorski.net/downloads/docs/InstallingConfiguringDevelopingWithXAMPP.pdf) by Dalibor Dvorski  to be extremely helpful, so I would suggest starting there.
1. What's the author of this article currently looking to master about XAMPP?
	> I'm aiming to tryout the following [article](http://www.ibm.com/developerworks/linux/library/l-xampp/) next, in order to see if I can add a lilttle something extra to my knowledge of XAMPP.

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAzMTU3NDIwOCwxMjM5NDY0MTA1XX0=
-->