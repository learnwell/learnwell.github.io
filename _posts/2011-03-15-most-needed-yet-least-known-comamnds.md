---

layout: postMod1
title: Most needed yet least known commands
author: pulkit
last_modified_at: July 12, 2020
tags: [grep,find,linx,unix,cygwin,cmd]

---


1. `dir /S *.ext`
    * Find a file or folder in Windows Command Prompt
1. `dir /X`
    * Find out the short names of a folder or file under the current directory in Windows Command Prompt
    * On PowerShell its a bit more involved: http://blogs.technet.com/b/heyscriptingguy/archive/2013/08/01/use-powershell-to-display-short-file-and-folder-names.aspx
1. `mklink <linkName> <target>`
    * It is used to create a <a href="http://en.wikipedia.org/wiki/NTFS_symbolic_link">symbolic link</a> in Windows Command Prompt. It is natively available in Windows Vista/2008+ (not in PowerShell or as an executable).
1. `find ./ -name *.ext`
    * Find a file or folder in Unix Shell
1. `find /var/lib/docker/volumes/*_error-logs -name '*.log' -mtime +15 | wc -l`
    * Count all the files of type `log` in directory `/var/lib/docker/volumes/*_error-logs` that are older than 15 days.
1. `find /var/lib/docker/volumes/*_error-logs -name '*.log' -mtime +15 -exec rm {} \;`
    * Delete all the files of type `log` in directory `/var/lib/docker/volumes/*_error-logs` that are older than 15 days.
1. `del /s /q targetFolder\*`
    * Remove all the files recursively from sub-folder as well as target folder in Windows Command Prompt
1. `rmdir /s /q targetFolder`
    * Remove all the files & folder recursively from sub-folder and at the end remove the target folder as well in Windows Command Prompt
1. `grep -lir "some text" *`
    * List all the files where "some text" is found, ignore case and search sub-directories recursively.
1. `grep -lr "bulkInsert" ~/ --include "*.js"`
    * search recursively through a specified location (in this case its ~/ which is the home directory) for any files that are of type .js and contain the string bulkInsert, pretty nice way to find lost things.
1. combine find and grep
    * ignore certain folders
    * look in package.json only
    * find case-insensitve matches to the word: `commit`
    * https://gist.github.com/pulkitsinghal/e634c08490432600c78bff561d887674.js
1. Lock a Mac running on Lion OS X
    * [Excerpt](http://docs.info.apple.com/article.html?path=Mac/10.7/en/mchlp2270.html):
        > "To lock your screen quickly with fast user switching enabled, choose Login Window from the menu with your user name. Your applications will remain open and undisturbed, but your computer islocked." You will find the "Login Window" immediately to the left of the Search (spotlight) Icon on the top right. Its your name that's written to the left of this search icon and this name can be clicked to reveal the "Login Window" option. And that's it, clicking it locks your mac.
    * [Shift-Command-Option-Q](http://www.macworld.com/article/49080/2006/01/lockscreen.html)
1. `diff -y /path/to/file1 path/to/file2`
    * Lines unique to the first file are displayed with a greater than sign `>` at their start, while lines unique to the second file start with a less than sign `<`. You might also consider using <u>the -y option to display the the two files in two columns</u>...</i>" ([Excerpt source](http://archive09.linux.com/feature/121476))



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk3OTcwNjk2NywxMzk3MDUyMDk4XX0=
-->