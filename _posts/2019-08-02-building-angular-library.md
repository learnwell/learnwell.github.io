---

layout: postMod1
title: Building an Angular Library
author: pulkit
last_modified_at: August 02, 2019
tags: [library,angular]

---

```
# step 1 - flavor A
ng new <lib-project-name> --create-application=false

# step 1 - flavor B
ng new <ngx-project-name> --create-application=false

# step 2 - say NO to router

# step 3 - select css, sass, scss, whatever you are comfortable with for styling. You may not need it at all if your library won't have any UI compnonents to it but you still need to pick something.

# step 4 - flavor A
cd <lib-project-name>

# step 4 - flavor B
cd <ngx-project-name>

# step 5 - flavor A
ng g lib <project-name> -p <lib>

# step 5 - flavor B
ng generate library <project-name> --prefix <lib>
```

## References
* [https://blog.angularindepth.com/how-to-build-a-component-library-with-angular-and-storybook-718278ab976#0864](https://blog.angularindepth.com/how-to-build-a-component-library-with-angular-and-storybook-718278ab976#0864)
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MTQwMzk1ODcsMTY2NDg2NzE0OCwxNT
AwMDczODE0XX0=
-->