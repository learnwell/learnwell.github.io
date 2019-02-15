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
-   It can even help you figure out how to configure a 3rd party dependency in LoopBack
	- For example, I wanted to use `express-xml-bodyparser` and started wondering if someone else had used it as a middleware in loopback before. `parse` was a phase in the middleware.json file where one might configure such a dependency. `params` was a standard way of providing input to the dependency being configured. I put all these keywords together with the fact that the configuration would happen in a JSON file and came up with a code search that helped me find the example code I wanted: [express-xml-bodyparser parse params language:json](https://github.com/search?q=express-xml-bodyparser+parse+params+language%3Ajson&type=Code&utf8=%E2%9C%93)
- Sometimes there are just too many search results when looking for loopback code on the angular/client side. This may happen because loopback’s auto-generated`lb-services.js` file, tends to contain many keywords. But you don’t want it to be searched! Well, you can exclude it. Look at the difference in the # of search results for the following code queries on github:
	- [loopback findbyid language:javascript path:/client NOT lbServices](https://github.com/search?utf8=%E2%9C%93&q=loopback+findbyid+language%3Ajavascript+path%3A%2Fclient+NOT+lbServices&type=Code&ref=searchresults) (close to 80)
	- [loopback findbyid language:javascript path:/client](https://github.com/search?utf8=%E2%9C%93&q=loopback+findbyid+language%3Ajavascript+path%3A%2Fclient&type=Code&ref=searchresults) (over 780)
-   Looking to limit your code search to Angular or client side? Append the following qualifiers as part of your search:
	-   path:/client
	-   path:/client/app    
	-   path:/client/js
-   Looking to limit your code search to Models or Remote Methods? Append the following qualifiers as part of your search:
	-   path:/common    
	-   path:/common/models
	-   path:/common/models language:json    
	-   path:/common/models language:javascript
-   Here’s a bucket list of various other loopback keyword searches I’ve run to help myself:
	- Wanted to figure out how to setup paging in loopback server side scripts
		- skip limit path:/server/boot
	-   Wanted to figure out how to use role resolver and loopback context together
		- registerResolver getCurrentContext
	- Wanted to figure out how to get at all the little extra metadata info that is hidden away in a Model
		- definition type language:javascript path:/common/models
	- findbyid user:strongloop language:javascript path:/client
	-app principal path:/common/models language:json
	-   findone language:javascript path:/client user:strongloop
	-   findone include filter path:/client
	-   properties id type user:strongloop language:javascript
	-   datasource type language:javascript path:/common/models
	-   properties id type language:javascript path:/common/models
	-   include relation language:javascript path:/client/app
	-   create language:javascript path:/client/js user:strongloop
	-   findById path:/client/js user:strongloop

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4Mzc3NDUzMSwtMTk5MjYyOTgxMCwtMT
YxOTgzMDI2M119
-->