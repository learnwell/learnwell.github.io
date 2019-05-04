---

layout: postMod1
title: How I like to setup my Visual Studio Code
author: pulkit
last_modified_at: April 20, 2019
tags: [mac,macbook,vscode]

---

## Too Long, Didn't Read.

1. Install
	``npm install --save-dev mocha chai ts-node typescript @types/chai @types/mocha`
`package.json`
```
"scripts": {
  "unit": "cross-env TS_NODE_COMPILER_OPTIONS='{ \"module\": \"commonjs\" }' mocha --require ts-node/register test/**/*.ts",
},
```
---

## Research
* https://journal.artfuldev.com/unit-testing-node-applications-with-typescript-using-mocha-and-chai-384ef05f32b2

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNTg0MDc1NjFdfQ==
-->