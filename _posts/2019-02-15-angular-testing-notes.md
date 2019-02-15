---  

layout: postMod1
title: Notes from Angular7 Component Testing
last_modified_at: February 15, 2018
tags: [angular, angular7]  

--- 

As of Feb 2019, episodes in the [13.x range](https://codecraft.tv/courses/angular/unit-testing/angular-test-bed/) on CodeCraft.tv are the best resource, known to me, for learning: *How to test components in Angular7*.

But even after absorbing all that goodness, I still found it difficult to add tests in an existing project. Most of it had to do with watch `ng test` fail and then figuring out all the dependencies that were unaccounted for.

Here is a list of gotchas:

* `ng-test` will fail due to missing dependencies which have not injection related m
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
 * For *material-design-bootstrap*, `imports:[MDBBootstrapModule]` isn't enough to configure it! You will see errors about random things like `ComponentLoaderFactory`:
	```
    Error: StaticInjectorError(DynamicTestModule)[ModalDirective -> ComponentLoaderFactory]: 
      StaticInjectorError(Platform: core)[ModalDirective -> ComponentLoaderFactory]: 
        NullInjectorError: No provider for ComponentLoaderFactory!
	```
	While the real issues is that it should be initialized with `forRoot()`
	```
	beforeEach(async () => {
      TestBed.configureTestingModule({
        declarations: [...],
        imports: [
          //MDBBootstrapModule // NO! NO!
          MDBBootstrapModule.forRoot() // YES
        ],
        providers: [...]
      }).compileComponents();
    });
	```
* *TBD...*

> Written with  [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMzE1NzE4NjVdfQ==
-->