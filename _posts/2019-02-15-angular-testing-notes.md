---  

layout: postMod1
title: Notes from Angular7 Component Testing
last_modified_at: May 03, 2018
tags: [angular, angular7]  

--- 

As of Feb 2019, episodes in the [13.x range](https://codecraft.tv/courses/angular/unit-testing/angular-test-bed/) on CodeCraft.tv are the best resource, known to me, for learning: *How to test components in Angular7*.

But even after absorbing all that goodness, I still found it difficult to add tests in an existing project. Most of it had to do with watch `ng test` fail and then figuring out all the dependencies that were unaccounted for.

Here is a list of gotchas:

* `ng test` will fail due to missing dependencies after you create a `spec` using tools that generate it for any existing component. Known tools: [angular-spec-generator](https://www.npmjs.com/package/angular-spec-generator) and [ngx-spec](https://github.com/smnbbrv/ngx-spec)
* Complaints about `ngModels`? That comes from `FormsModule` so if the component being tested uses that then you inject it via `imports: [FormsModule]`
* If you see complaints about missing `HttpClient` and/or `HttpHandler`, instead of configuring the `providers`:
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
	You should configure the `imports`:
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
* Complaints about `mdbModal`? That comes from `MDBBootstrapModule` so if the component being tested uses that then you inject it via `imports: [MDBBootstrapModule.forRoot()]`
 * For *material-design-bootstrap*, if you **misconfigure** it as `imports:[MDBBootstrapModule]` then you will see random errors like:
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
* Complaints about `routerLink`?
	* Don't use the combination of`imports:[RouterModule]` and `providers:[Router]`
	* Use `imports:[RouterTestingModule.withRoutes(routes)]`
	* You can view CodeCraft [episode 13.13](https://codecraft.tv/courses/angular/unit-testing/routing/) to watch this done the right way.
* Complaints about `zone` or `injector`
	```
	# can't find the zone dependency
    Failed: Zone is needed for the async() test helper
              but could not be found. Please make sure
              that your environment includes
              zone.js/dist/zone.js
    # testbed hasn't been initialized
    Failed: Cannot read property 'injector' of null
	```
    Usually all of this is available in `src/test.ts` and used by `ng test` automatically ... but is you use `protractor` as the entrypoint, then you must incorporate workarounds into `e2e/protractor.conf.js` file's `onPrepare()` method somehow.
    * Relevant Stack Overflow posts
	    * https://stackoverflow.com/questions/40699593/cannot-read-property-injector-of-null-jasmine-angular-2#answer-40699740
		    * https://github.com/angular/quickstart/blob/master/karma-test-shim.js#L75
	    * https://github.com/angular/quickstart/blob/master/karma-test-shim.js#L75
* *TBD...*

> Written with  [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY3MjMxODYzMiwtMTc3ODgzOTM3MCwtOT
M5MDAyODM2LC03MTA4ODc2NTgsLTE2NDk4NjQ3MV19
-->