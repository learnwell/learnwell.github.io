
---

layout: post
title: An ideal `bash_profile` - better history upkeep
author: pulkit
tags: []

---

## Short & sweet
Get it from here:
https://gist.github.com/pulkitsinghal/077fd7d083c9c4fe7336

## With explanations

```
export HISTCONTROL=erasedups
export HISTFILESIZE=1000000
export HISTSIZE=10000
export HISTIGNORE="&:[ ]*:exit:clear:ls:cd:pwd"
```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNTk5NTczMjZdfQ==
-->