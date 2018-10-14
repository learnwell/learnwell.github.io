---

layout: post
title: Using StackEdit with Jekyll and Github Pages!
author: pulkit

---

My goal was to figure out how I can use **StackEdit** as an editor for blogs that are built by **Jekyll** and hosted on **Github Pages**.

## Next Steps:
* Create a workspace that encapsulates _drafts and _posts and all the other folders in the jekyll [folder structure](https://jekyllrb.com/docs/structure/).
* Figure out how to move or publish the posts that are sitting as drafts.

## Progress thus far:

1. Created a new account on GitHub to circumvent the scary/annoying fact that StackEdit requires complete access to all private repos in a GitHub account before they can be used together.
2. Created a repo named `<username>.github.io` because that is the de-facto standard for the project that automatically becomes hosted as a GitHub Page website.
3. Selected the [Theme Chooser](https://help.github.com/articles/adding-a-jekyll-theme-to-your-github-pages-site-with-the-jekyll-theme-chooser/)'s `hack` theme and it automatically generated the first two **jekyll**-oriented files in the project for me.
4. Created a new workspace in StackEdit:
    * `Workspaces > Add a GitHub backed workspace`
        * Repo URL: `https://github.com/<username>/<username>.github.io`
        * Folder Path: `_drafts`
        * Branch: `master`
5. Renamed the welcome file to: `using-stackedit-with-jekyll-and-github-pages`
6.  Switched over to my github repo and confirmed that the file had been created inside the appropriate directory, with the appropriate file extension: `_drafts/using-stackedit-with-jekyll-and-github-pages.md`

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNjUyMjQzOTFdfQ==
-->