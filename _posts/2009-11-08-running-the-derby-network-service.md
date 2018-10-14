---

layout: post
title: Running the Derby-Network-Service
author: pulkit

---

Since Derby is all about having a file-like database on your hard-drive, its generally a good idea to have one location on you development machine of choice, where you can place a derbynet folder for all your derby network access needs.

For example:
* `c:\apps\derbynet` (win flavor)
* `/opt/derbynet` ('nix flavor)

Ok! But what should this general purpose folder contain? The files in this folder should be the ones from Derby's `lib` package. You can also create something along the lines of the following files as the start and stop commands under the derbynet folder:

* `startDerbyNet.sh` could contain the following lines:

	```
	export CLASSPATH=/path/to/derby.jar:/path/to/derbytools.jar:/path/to/derbynet.jar:$CLASSPATH
	java org.apache.derby.drda.NetworkServerControl start -h <ip-address> -p 1527
	```
* `stopDerbyNet.sh` could contain the following lines:

	```
	export CLASSPATH=/path/to/derby.jar:/path/to/derbytools.jar:/path/to/derbynet.jar:$CLASSPATH
	java org.apache.derby.drda.NetworkServerControl shutdown -h <ip-address> -p 1527
	```

And then you can call upon these scripts like so:

* `/opt/derbynet/startDerbyNet.sh > derbynet.logs &` 
* `/opt/derbynet/stopDerbyNet.sh`

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNDQ4NzY5NTIsMTA5MDY5NjUyNSwxOD
U5NDAyNDIyLC05OTkwOTA5NDNdfQ==
-->