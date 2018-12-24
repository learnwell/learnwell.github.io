---

layout: page
title: Tips & Tricks for Blogging
permalink: /blogging/
tags: [blog, blogs, blogging, tip, tips, trick, tricks]

---

* Use [sylhare/Type-on-Strap](https://github.com/sylhare/Type-on-Strap#usage) as a starter template for creating a *Jekyll* and *GitHub Pages* based blog.
* Enabling Emojis for GitHub Pages in Jekyll posts
	* https://help.github.com/articles/emoji-on-github-pages/
* Use Icons & Emojis in Jekyll posts written via StackEdit
	* [Caveat](https://github.com/benweet/stackedit/issues/1133): 
		* [Older icons](https://stackedit.io/res/libs/fontello/demo.html) provided in stackedit v4 were deprecated.
		* [Current icons](https://www.webpagefx.com/tools/emoji-cheat-sheet/) used here are what's supported for stackedit v5.
* Expand/collapse content in Jekyll posts
	* [Discussion and Examples 1](https://gist.github.com/ericclemmons/b146fe5da72ca1f706b2ef72a20ac39d#gistcomment-1817140)
	* [Discussion and Examples 2](https://github.com/gettalong/kramdown/issues/155#issuecomment-339793629)
* Escape Liquid template tags in Jekyll posts
	* [Article](https://sarathlal.com/escape-liquid-tag-in-jekyll-posts/)
* Add `Table of Contents` to Jekyll posts
	```
	{% raw %}
	* TOC
	{:toc}
	{% endraw %}
	```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMzM1OTgzMjYsLTY3MzM5NDAzNiwxND
A0MTExNzE0XX0=
-->