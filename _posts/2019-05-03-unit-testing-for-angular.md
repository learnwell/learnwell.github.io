---

layout: postMod1
title: Unit Testing for Angular
author: pulkit
last_modified_at: April 20, 2019
tags: [unit,test,angular]

---

## Problem Statement

Component testing runs via `ng test` and there is no way to specify the specific test you are interested in. This means wasting time sorting out and fixing generated specs that are failing because they don't recognize your component selectors.

Component tests are unit tests by nature so they can't be run via `protractor`.

`JEST` may be a viable alternative.

Or you can be clever and move the code you need to test into utility classes then run mocha

## Solution

1. Install
	```
	npm install --save-dev mocha chai \
	  ts-node typescript \
	  @types/chai @types/mocha
	```
2. Update `package.json`
	```
	"scripts": {
	  "unit": "cross-env TS_NODE_COMPILER_OPTIONS='{ \"module\": \"commonjs\" }' mocha --require ts-node/register test/**/*.ts"
	}
	```
3. Create test
	```
	import { describe } from  'mocha';
	import  *  as  moment  from  'moment';
	import  *  as  chai  from  'chai';
	var  expect  =  chai.expect;
	describe('describe-block', () => {
	  it('it-block', () => {
	    expect(true).to.equal(true);
	  });
	});
	```
1. Run it: `npm run unit`

---

## Research
* [Unit testing node applications with TypeScript — using mocha and chai](https://journal.artfuldev.com/unit-testing-node-applications-with-typescript-using-mocha-and-chai-384ef05f32b2)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAyMjg3NTA0N119
-->