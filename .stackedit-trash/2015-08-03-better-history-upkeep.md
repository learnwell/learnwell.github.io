
---
layout: post
title: An ideal `bash_profile` - better history upkeep
author: pulkit
tags: [history,CLI,terminal,bashrc,bash,profile]

---



```
export HISTCONTROL=erasedups
export HISTFILESIZE=1000000
export HISTSIZE=10000
export HISTIGNORE="&:[ ]*:exit:clear:ls:cd:pwd"
```





> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc5ODExMzkzMV19
-->