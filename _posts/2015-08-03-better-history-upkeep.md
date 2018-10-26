
---

layout: post
title: An ideal `bash_profile` - better history upkeep
author: pulkit
tags: []

---

Whether you are setting up you local `'nix` machine or your remote one, having the terminal history configured properly is a great boon and best practice.

```
export HISTCONTROL=erasedups
export HISTFILESIZE=1000000
export HISTSIZE=10000
export HISTIGNORE="&:[ ]*:exit:clear:ls:cd:pwd"
```

## Reference(s)

* https://gist.github.com/pulkitsinghal/077fd7d083c9c4fe7336


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjIxOTAzNDldfQ==
-->