---  

layout: postMod1
title: Use GitHub when new frameworks don't document what you need
last_modified_at: April 6, 2016
tags: [angular, angular7]  

--- 

GitHub is an invaluable resource. Let's take the example of trying to figure out "the unknown" when a framework such as  LoobackJS is involved:
-   There are plenty of public projects that use loopback.
-   When in doubt, you can use code search to find syntax and other clues on how to perform certain tasks.
-   There are many ways to [narrow down](https://help.github.com/articles/searching-code/) search results, the keywords from an API search also apply to what you type in the searchbox on github: [https://developer.github.com/v3/search/#considerations-for-code-search](https://developer.github.com/v3/search/#considerations-for-code-search)
-   But keep in mind: Forked projects will not be searched by GitHub unless they have more STARS than their parent.![](https://lh6.googleusercontent.com/_zPIzX78nxw3BIgBrwP7tP2kfALx1N7XOj8dfSMOvaKFp0MBEmbbqWTxR5m2HUVAVJvJq2wUgv7nzHFlYtheDZUxwQ77DtmKXIPI51RhxZ5PMyiiCDDzhvs0Ae8PKJXN1nrEQDxeStE)
-   Need a code example for how to use `findById` in angular or client side? Search GitHub with keywords and search qualifiers::
    - [findbyid language:javascript path:/client](https://github.com/search?q=findbyid+language%3Ajavascript+path%3A%2Fclient&type=Code&utf8=%E2%9C%93)
-   Need to narrow down results further by a GitHub username of organization name?
	- [findbyid user:strongloop language:javascript path:/client](https://github.com/search?utf8=%E2%9C%93&q=findbyid+user%3Astrongloop+language%3Ajavascript+path%3A%2Fclient&type=Code&ref=searchresults)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5OTI2Mjk4MTAsLTE2MTk4MzAyNjNdfQ
==
-->