---

layout: postMod1
title: Angular CLI woes: Part 1
author: pulkit
last_modified_at: February 05, 2018
tags: [angular,angular6,CLI,ng]

---

I wanted to generate a directive with `ng g directive` but the CLI feedback was quite un-intuitive!

```
$ ng g directive
...
Cannot read property 'lastIndexOf' of undefined
```

Could it be that it wanted one more argument and this command wasn't built to prompt me with options? Yup! `ng g directive myDirectiveName` worked, but what a waste of time :/

Why angular why?

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMDg4NjUzNzNdfQ==
-->