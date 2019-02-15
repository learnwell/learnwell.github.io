---  

layout: postMod1
title: Notes from Angular7 Component Testing
last_modified_at: February 15, 2018
tags: [angular, angular7]  

--- 

As of Feb 2019, episodes in the [13.x range](https://codecraft.tv/courses/angular/unit-testing/angular-test-bed/) on CodeCraft.tv are the best resource, known to me, for learning: *How to test components in Angular7*.

But even after absorbing all that goodness, I still found it difficult to add tests in an existing project. This is because it was a fairly mature angular project and the dependency injection required quite a lot of work.

Here is a list of some gotchas

* When it starts complaining about missing `HttpClient` and `HttpHandler`, instead of configuring the `TestBed` like this:
	```
	beforeEach(async () => {
      TestBed.configureTestingModule({
        declarations: [...],
        imports: [],
        providers: [
          HttpClient,
          HttpHandler
        ]
      }).compileComponents();
    });
	```
	You should set it up like so instead:
	```
	beforeEach(async () => {
      TestBed.configureTestingModule({
        declarations: [...],
        imports: [
          HttpClientModule
        ],
        providers: [...]
      }).compileComponents();
    });
	```
 * asdasd


> Written with  [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQyNjg2NTUxM119
-->