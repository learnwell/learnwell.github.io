---

layout: page
title: Blogging
permalink: /blogging/
last_modified_at: April 14, 2020
tags: [blog, blogs, blogging, tip, tips, trick, tricks]

---

* Embed GIFs into the Jekyll based blog that's hosted on Github Pages and edited via StackEdit
	* [Format](https://github.com/tiimgreen/github-cheat-sheet#user-content-imagesgifs) the raw github URL
	* [Adjust](https://stackoverflow.com/questions/14675913/changing-image-size-in-markdown#answer-21242579) the size as needed
	* Works within StackEdit but not on the published blog:
    ```
    ![Demo](https://github.com/learnwell/learnwell.github.io/raw/master/assets/img/input-focus-within-modal.gif =350x)
    ```
    * Works both places:
    ```
	<img src="https://github.com/learnwell/learnwell.github.io/raw/master/assets/img/input-focus-within-modal.gif" width="350"/>
	```
* Use [sylhare/Type-on-Strap](https://github.com/sylhare/Type-on-Strap#usage) as a starter template for creating a *Jekyll* and *GitHub Pages* [based blog]({% post_url using-stackedit-with-jekyll-and-github-pages %}).
* Emojis in Jekyll posts
	1. <u>On Mac</u>, use `ctrl+cmd+space` and select the emoji to embed directly.
	2. [Emojis on GitHub Pages](https://help.github.com/articles/emoji-on-github-pages/) sometimes break as versions come & go with `Jekyll + kramdown + Github Pages` combination so I've stopped trusting it.
	3. Using markdown when writing via <u>StackEdit</u> sometimes breaks as versions come & go with `Jekyll + kramdown + Github Pages` combination so I've stopped trusting it.
		* [Caveat](https://github.com/benweet/stackedit/issues/1133): 
			* [Older icons](https://stackedit.io/res/libs/fontello/demo.html) provided in stackedit v4 were deprecated.
			* [Current icons](https://www.webpagefx.com/tools/emoji-cheat-sheet/) used here are what's supported for stackedit v5.
* Expand/collapse content in Jekyll posts
	* [Discussion and Examples 1](https://gist.github.com/ericclemmons/b146fe5da72ca1f706b2ef72a20ac39d#gistcomment-1817140)
	* [Discussion and Examples 2](https://github.com/gettalong/kramdown/issues/155#issuecomment-339793629)
* Escape Liquid template tags in Jekyll posts
	* [Article](https://sarathlal.com/escape-liquid-tag-in-jekyll-posts/)
* Add `Table of Contents` to Jekyll posts
* [List](https://pages.github.com/versions/) of supported `jekyll plugins` for `github pages`
	```
	{% raw %}
	* TOC
	{:toc}
	{% endraw %}
	```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc2ODM2NzI1LDE3NTAzMzc2ODAsMTg1OD
U5NDk2MSwtMTk2NzU0NDc4MV19
-->