---

layout: postMod1
title: How I like to setup my Mac
author: pulkit
last_modified_at: February 03, 2019
tags: [mac,macbook,chrome,setup]

---

1. Tweak how history is maintained in `terminal` because whether you are setting up you local `'nix` machine or your remote one, having the terminal history configured properly is a great boon and best practice.
	* Quickie:
	```
	export HISTCONTROL=erasedups
    export HISTFILESIZE=1000000
    export HISTSIZE=10000
	export HISTIGNORE="&:[ ]*:exit:clear:ls:cd:pwd"
	```
	* A more thorough [script](https://gist.github.com/pulkitsinghal/077fd7d083c9c4fe7336) for those so inclined.
2. Remove touchpad gestures to avoid accidentally navigating backward/forward within Chrome
	* One Variation - Open `terminal` and run:
		```
		defaults write com.google.Chrome AppleEnableSwipeNavigateWithScrolls -bool FALSE
		```
	* If that doesn't work then another Variation - Open `terminal` and run:
		```
		defaults write com.google.Chrome.plist AppleEnableSwipeNavigateWithScrolls -bool FALSE
		```
	* Credit for this solution goes to [OSXDaily](http://osxdaily.com/2015/05/09/disable-swipe-navigation-google-chrome-mac/)
3. *more to come*

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc1ODE3OTI0LDQyMDk4NDA1OV19
-->