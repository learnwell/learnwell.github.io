---

layout: postMod1
title: How to perform logical OR in Firebase
author: pulkit
last_modified_at: August 02, 2019
tags: [OR,firebase,query,logical,nosql,data,modeling]

---

This [video]( https://youtu.be/35RlydUf6xo?t=198) offers a great example of how: "In order to combine multi-tag match, the `tags` field must be a map" and we must merge results and remove duplicates on client side after running individual queries.

But there wasn't any example for client side code to do so, until I found a plausible suggestion on [stackoverflow](https://stackoverflow.com/questions/46632042/how-to-perform-compound-queries-with-logical-or-in-cloud-firestore#answer-48832819).

> bind two Observables using the rxjs merge operator.

```
import { Observable } from 'rxjs/Observable';
import 'rxjs/add/observable/merge';

...

getCombinatedStatus(): Observable<any> {
   return Observable.merge(
     this.db.collection('foo', ref =>
      ref.where('tags.physics','==','true')).valueChanges(),
     this.db.collection('foo', ref => ref.where('tags.chemistry','==','true')).valueChanges());
}

```

Then you can subscribe to the new Observable updates using the above method:

```
getCombinatedStatus.subscribe(results => console.log(results);
```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk1NDg3NDMyXX0=
-->