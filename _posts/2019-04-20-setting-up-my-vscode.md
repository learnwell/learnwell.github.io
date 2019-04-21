---

layout: postMod1
title: How I like to setup my Visual Studio Code
author: pulkit
last_modified_at: April 20, 2019
tags: [mac,macbook,vscode]

---

* `keybindings.json`
    ```
    // Place your key bindings in this file to override the defaultsauto[]
	[
	    {
	        "key": "shift+cmd+o",
	        "command": "workbench.action.quickOpen"
	    },
	    {
	        "key": "cmd+]",
	        "command": "workbench.action.navigateForward"
	    },
	    {
	        "key": "cmd+1",
	        "command": "-workbench.action.focusFirstEditorGroup"
	    },
	    {
	        "key": "cmd+1",
	        "command": "bookmarks.toggle",
	        "when": "editorTextFocus"
	    },
	    {
	        "key": "cmd+s",
	        "command": "workbench.action.files.saveAll"
	    },
	    {
	        "key": "cmd+[",
	        "command": "-editor.action.outdentLines",
	        "when": "editorTextFocus && !editorReadonly"
	    },
	    {
	        "key": "cmd+[",
	        "command": "workbench.action.navigateBack"
	    },
	    {
	        "key": "ctrl+-",
	        "command": "-workbench.action.navigateBack"
	    },
	    {
	        "key": "cmd+]",
	        "command": "-editor.action.indentLines",
	        "when": "editorTextFocus && !editorReadonly"
	    },
	    {
	        "key": "cmd+u",
	        "command": "-cursorUndo",
	        "when": "textInputFocus"
	    },
	    {
	        "key": "cmd+u",
	        "command": "editor.action.transformToUppercase"
	    },
	    {
	        "key": "cmd+l",
	        "command": "-expandLineSelection",
	        "when": "textInputFocus"
	    },
	    {
	        "key": "cmd+l",
	        "command": "workbench.action.gotoLine"
	    },
	    {
	        "key": "ctrl+g",
	        "command": "-workbench.action.gotoLine"
	    },
	    {
	        "key": "cmd+e",
	        "command": "-actions.findWithSelection"
	    },
	    {
	        "key": "cmd+e",
	        "command": "emmet.expandAbbreviation"
	    }
	]
    ```

## Related

* [How I like to setup my Mac](https://learnwell.github.io/2018/12/28/setting-up-my-mac.html)
* [Deploy MySql in 60 seconds](https://learnwell.github.io/2019/03/01/run-mysql-locally-in-docker-for-development.html)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM4NTEwNzY5XX0=
-->