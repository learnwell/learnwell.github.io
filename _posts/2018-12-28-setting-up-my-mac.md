---

layout: postMod1
title: How I like to setup my Mac
author: pulkit
last_modified_at: February 26, 2019
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
1. Show hidden fiels 
1. Setup `nvm` instead of installing node directly
	  * Out of all the methods listed [here](https://blog.theodo.fr/2016/01/speed-up-npm-install-with-a-nexus-proxy-to-cache-packages/), I preferred the one that uses `npm-cache`:
		```bash
		$ nvm use 9
		Now using node v9.11.2 (npm v5.6.0)
		$ npm install -g npm-cache
		$ cd /path/to/yourProject
		$ npm-cache install
		[npm-cache] [INFO]
		  using /Users/<username>/.package_cache
		  as cache directory
		##
		# You can also switch nodejs version
		# the npm-cache will become specific
		# to that version, as it should
		##
		$ nvm use 11
		Now using node v11.8.0 (npm v6.5.0)
		$ npm install -g npm-cache
		$ cd /path/to/yourProject
		$ npm-cache install
		[npm-cache] [INFO]
		  using /Users/<username>/.package_cache
		  as cache directory
		```
	* There may be some room for improvement by changing cache directory from `/Users/<username>/.package_cache` to the relevant nodejs version's directory:
		```bash
		$ ls ~/.nvm/versions/node/v11.8.0/lib/node_modules/
		ionic
		npm
		.package_cache # hypothetical, I haven't done it yet

		$ ls ~/.nvm/versions/node/v9.11.2/lib/node_modules/
		@angular
		angular-spec-generator
		firebase-tools
		npm
		npm-cache
		.package_cache # hypothetical, I haven't done it yet
		```
		* Ideas
			* ```ls -alrt ~/.nvm/versions/node/`nvm current`/.package_cache``` works in terminal
			* I tried
				```
				npm-cache \
				  install \
				  --cacheDirectory ~/.nvm/versions/node/`nvm current`/.package_cache
				``` 
			* It did **NOT** work, filed an issue [here](https://github.com/swarajban/npm-cache/issues/107)
1. *more to come*

## Open Questions

* Using `nvm` and `npm-cache` together
	* There may be some room for improvement by changing cache directory from `/Users/<username>/.package_cache` to the relevant nodejs version's directory:
		```bash
		$ ls ~/.nvm/versions/node/v11.8.0/lib/node_modules/
		ionic
		npm
		.package_cache # hypothetical, I haven't done it yet

		$ ls ~/.nvm/versions/node/v9.11.2/lib/node_modules/
		@angular
		angular-spec-generator
		firebase-tools
		npm
		npm-cache
		.package_cache # hypothetical, I haven't done it yet
		```
		* Ideas
			* ```ls -alrt ~/.nvm/versions/node/`nvm current`/.package_cache``` works in terminal
			* I tried
				```
				npm-cache \
				  install \
				  --cacheDirectory ~/.nvm/versions/node/`nvm current`/.package_cache
				``` 
			* It did **NOT** work ... filed an issue [here](https://github.com/swarajban/npm-cache/issues/107)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQwMDkxMjkxLC02NzM1MjY5NjIsNTU3OD
M0MTcwLC0xMDg0MzA0MDg0LC0xMDAyMzM0OCwtNzU4MTc5MjQs
NDIwOTg0MDU5XX0=
-->