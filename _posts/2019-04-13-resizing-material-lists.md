---

layout: postMod1
title: Resizing a list in Angular Material
author: pulkit
last_modified_at: April 13, 2019
tags: [angular,material,mat-list,mat-list-item,textarea,cdkTextareaAutosize]

---

How to increase `mat-list` height with an increase in textarea height?

## Usecase

I have a `mat-list` where one of the `mat-list-item`s is a `textarea` can be resized automatically via angular CDK's `cdkTextareaAutosize`. But unfortunately, the textarea's contents **overflow** into other items!

Here's the [stackblitz](https://stackblitz.com/edit/mat-list-height?embed=1&file=src/app/app.component.html) so you can see the issue firsthand. Go ahead and try editing multiline data within the textarea and take it anywhere from 1 to 6 rows to more.

## Question

Is there a way to trigger the mat-list and/or mat-list-item to update its height after `cdkTextareaAutosize` directive is done modifying the textarea's height?

## Research

* I've looked into https://github.com/angular/material2/issues/8707 and that's a different question because they were talking about a textarea that started with a fixed # of rows but in my case the textarea row height can change between 1 and 6.

## Solution
Originally when I tried their [solution](https://github.com/angular/material2/issues/8707) of overriding default material styles … it did not work because I altered it such that the [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) wasn’t high enough but later I understood what they were saying set the specificity correctly and then it worked!

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTY2NjQ0MTcyXX0=
-->