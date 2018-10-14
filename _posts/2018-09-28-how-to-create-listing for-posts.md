---

layout: post
title: How to create a listing of available blog posts
author: pulkit

---

Today I started out with a goal to post over my oldest blog from google's blogger/blogspot and have it show up on github pages via Jekyll magic.

I created `_posts/2009-11-08-running-the-derby-network-service.md` but wasn't quite sure what URL Jekyll might have placed the generated html content at.

This got me wondering if my theme of choice - `jekyll-theme-hacker` had a "mode" where the default landing page could be configured to show:
* a table-of-contents, or
* a listing-of-posts, or
* a navigation menu, or
* recent-posts

... or any such concept?

----

Googling showed, I was not alone! There were [others](https://github.com/walfud) with similar [queries](https://github.com/pages-themes/slate/issues/23).
	> Hi, I like your theme very well. But after I fork & deploy to my github-pages, and have some article, I even can't have a index page for all my posts. That's a pity.  
Is there anyway to generate directory for all my post automatically?

But the remedies ***did not*** seem markdown-centric and I did not wish to dabble in HTML yet.

* [Displaying an index for posts](https://jekyllrb.com/docs/posts/#displaying-an-index-of-posts)
* [List Author's Posts](https://jekyllrb.com/docs/step-by-step/09-collections/#list-authors-posts)

----

The github theme generator had created an `index.md` file which meant that Jekyll must be mixing its content into some sort of parent `index.html` with layouts and what not provided by the theme itself. 

I began pondering if it was at all possible to use the templating language - [Liquid](https://jekyllrb.com/docs/liquid/) - within markdown.

With `site.posts` as a keyword/clue, I created a [search query](https://github.com/search?utf8=%E2%9C%93&q=filename%3Aindex.md+%22site.posts%22+jekyll&type=) to find any and all code on github where someone might have used liquid templating syntax inside markdown.

Turns out, its entirely possible and supported to add templating syntax inside markdown. And that was that ... by adding only the following lines to the bottom (anywhere is fine really) of my `index.md` I could finally access my migrated post!

```
{% for post in site.posts %}

* {{ post.date | date_to_string }} » [{{post.title}}]({{ post.url }})

{% endfor %}
```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAxNDI1MDk3Ml19
-->