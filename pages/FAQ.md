---

layout: postMod1
title: FAQ
author: pulkit
last_modified_at: February 27, 2019
tags: []

---

* How to attach and monitor logs in CLI (mac terminal) for a detached container that was started using `docker-compose`?
	```
	docker-compose logs --follow <serviceName>
	```
* How to write commands that readers can copy/paste to create and populate a file from their CLI?
	* [Article 1]https://stackoverflow.com/questions/40562595/creating-an-output-file-with-multi-line-script-using-echo-linux/40562814#40562814
	* [Article 2](https://unix.stackexchange.com/questions/77277/how-to-append-multiple-lines-to-a-file
		```
		echo "
		line 1
		  line 2
		line 3
		" >> yourFileName.ext
		```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5ODUxNDYzMDYsLTE2NTY4MTgwNzddfQ
==
-->