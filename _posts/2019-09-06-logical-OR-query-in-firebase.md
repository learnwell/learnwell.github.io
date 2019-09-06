---

layout: postMod1
title: How to perform logical OR in Firebase
author: pulkit
last_modified_at: September 06, 2019
tags: [OR,firebase,query,logical,nosql,data,modeling]

---

## Starting out
This [video]( https://youtu.be/35RlydUf6xo?t=198) offers a great example of how: "In order to combine multi-tag match, the `tags` field must be a map" and we must merge results and remove duplicates on client side after running individual queries.

## Client Side
But there wasn't any example for client side code to do so, until I found a plausible suggestion on [stackoverflow](https://stackoverflow.com/questions/46632042/how-to-perform-compound-queries-with-logical-or-in-cloud-firestore#answer-48832819).

> Bind two Observables using the rxjs merge operator

```
import { Observable } from 'rxjs/Observable';
import 'rxjs/add/observable/merge';

...

getCombinatedStatus(): Observable<any> {
  return Observable.merge(
    this.db.collection('foo', ref =>
      ref.where('tags.physics','==','true')).valueChanges(),
    this.db.collection('foo', ref =>
      ref.where('tags.chemistry','==','true')).valueChanges());
}
```

> Then subscribe to the new Observable updates using the `getCombinatedStatus()` method.

```
getCombinatedStatus.subscribe(results => console.log(results);
```

## Server Side "niche" Workaround

There was [another](https://stackoverflow.com/questions/46632042/how-to-perform-compound-queries-with-logical-or-in-cloud-firestore#answer-55151765) great solution if it fits your dataset. Also a [blog](https://blog.oasisdigital.com/2018/querying-without-or-in-firestore/#post-2022-_adhx5di43dpw) discussing the same strategy. And a github [issue](https://github.com/firebase/firebase-js-sdk/issues/1777) on the topic.

> The only possible values for ours are A,B,C,D (4) so we have to query for things like `A||B, A||C, A||B||C` etc

> So if something only qualified for conditional  `A`  of our 4 conditionals (A,B,C,D) then its array would contain the following literal strings: 

```
tags: [
  "A",
  "A||B",
  "A||C",
  "A||D",
  "A||B||C",
  "A||B||D",
  "A||C||D",
  "A||B||C||D"
 ]
```

> Then for any of those  `OR`  combinations we can just search  `array-contains`  on whatever we may want (e.g. `A||C`)

I assume some work (worker and client) would go into handling case-sensitivity and alphabetical sorting, both when creating, deleting, updating the tags ... and especially when querying/reading them.

## Brainstorming

How about assigning each `tag` a permanent prime number when i its created and using product of two or more such tags as the combination being placed inside `tags[]` or `tags{}`?

## References
*  https://youtu.be/35RlydUf6xo?t=198
* https://stackoverflow.com/questions/46632042/how-to-perform-compound-queries-with-logical-or-in-cloud-firestore#answer-48832819
* https://stackoverflow.com/questions/46632042/how-to-perform-compound-queries-with-logical-or-in-cloud-firestore#answer-55151765
* https://github.com/firebase/firebase-js-sdk/issues/1777
* https://blog.oasisdigital.com/2018/querying-without-or-in-firestore/#post-2022-_adhx5di43dpw

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzc0ODY4MjQzLC0xNzM3MTY4OTU4LDE2MT
g1NzUyOF19
-->