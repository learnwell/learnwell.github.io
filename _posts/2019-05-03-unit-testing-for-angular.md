---

layout: postMod1
title: Unit Testing for Angular
author: pulkit
last_modified_at: April 20, 2019
tags: [unit,test,angular]

---

## Problem Statement

Component testing runs via `ng test` and there is no way to specify the specific test you are interested in. This means wasting time sorting out and fixing generated specs that are failing because they don't recognize your component selectors.

* Component tests are unit tests by nature so they can't be run via `protractor`.
* `JEST` may be a viable alternative.

Or you can be clever and move the code, which you want to test, into utility classes. Then run mocha with support for typescript compilation!

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
3. Create `test/test.ts`
	```
	import { describe } from 'mocha';
	import * as moment from 'moment';
	import * as chai from 'chai';
	var  expect  =  chai.expect;

	import { MyComponent } from './../src/app/my/my.component';

	describe('describe-block', () => {
	  it('it-block', () => {
	    expect(true).to.equal(true);

	    let myComponent = new MyComponent();
	    expect(myComponent.sayBlue()).to.equal('blue');
	  });
	});
	```
1. Run it: `npm run unit`

---

## Research
* [Unit testing node applications with TypeScript — using mocha and chai](https://journal.artfuldev.com/unit-testing-node-applications-with-typescript-using-mocha-and-chai-384ef05f32b2)
* [Running unit tests selectively with Angular7](https://blog.oldcomputerjunk.net/2019/ng7-selective-karma/)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU3NjQ1NzU3NywtMjcxODg4NTVdfQ==
-->