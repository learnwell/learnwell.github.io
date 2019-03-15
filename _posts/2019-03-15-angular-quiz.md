---

layout: postMod1
title: Angular Quiz - Question of the Day
author: pulkit
last_modified_at: March 10, 2019
tags: [Angular Quiz]

---

### Which of the following is the correct way to utilize Angular Form's template-driven approach?

  - [ ] Option **A**
	   ```
    <!-- .html -->
    <form (ngSubmit)="onSubmit(formLocalRef)" #formLocalRef>
	   ...
	</form>
	```
	```
	// .component.ts
	onSubmit(formLocalRef: HTMLFormElement) {
	  // do stuff with thisForm
	}
	```
  - [ ] Option **B**
	   ```
    <!-- .html -->
    <form (ngSubmit)="onSubmit()" #thisForm>
	   ...
	</form>
	```
	```
	// .component.ts
	@ViewChild('formByLocalRef') form: HTMLFormElement;
	onSubmit() {
	  // do stuff with this.thisForm
	}
	```
  - [ ] Option **C**
	   ```
    <!-- .html -->
    <form (ngSubmit)="onSubmit()" #thisForm="ngForm">
	   ...
	</form>
	```
	```
	// .component.ts
	onSubmit(thisForm: HTMLFormElement) {
	  // do stuff
	}
	```


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk3NzA1Mjk2XX0=
-->