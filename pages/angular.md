
---  

layout: page
title: Angular
permalink: /angular/  
last_modified_at: February 15, 2018
tags: [angular, angular7]  

--- 

As of Feb 2019, episodes in the [13.x range](https://codecraft.tv/courses/angular/unit-testing/angular-test-bed/) on CodeCraft.tv are an excellent resource for learning how to test components in Angular7.

But even after absorbing all that goodness, I still found gaps when adding tests to an existing component is a fairly mature angular project.

Here is a list of some gotchas

* Instead of configuring
  ```
  beforeEach(async () => {
    TestBed.configureTestingModule({
      declarations: [...
      ],
      imports: [
        HttpClientModule,
        
      ],
      providers: [
        StoreService // meant to be rx like
      ]
    }).compileComponents();
  });
  ```
 * asdasd


> Written with  [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEzOTE1NTg2OF19
-->