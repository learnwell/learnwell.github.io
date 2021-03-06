---

layout: postMod1
title: Angular Quiz - Question of the Day
author: pulkit
last_modified_at: March 15, 2019
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
	  // do stuff with formLocalRef
	}
	```
  - [ ] Option **B**
	   ```
    <!-- .html -->
    <form (ngSubmit)="onSubmit()" #formLocalRef>
	   ...
	</form>
	```
	```
	// .component.ts
	@ViewChild('formLocalRef') form: HTMLFormElement;
	onSubmit() {
	  // do stuff with this.formLocalRef
	}
	```
  - [x] Option **C**
	   ```
    <!-- .html -->
    <form (ngSubmit)="onSubmit()" #formLocalRef="ngForm">
	   ...
	</form>
	```
	```
	// .component.ts
	@ViewChild('formLocalRef') form: NgForm;
	onSubmit() {
	  // do stuff with formLocalRef
	}
	```


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MDQ5NTM0MjcsMTM0NDUxMTk1NF19
-->