---

layout: postMod1
title: Saving to FireStore via AngularFire and TypeScript lacks polish
author: pulkit
last_modified_at: March 10, 2019
tags: [firestore,firebase,angularfire]

---

When working on a simplistic `save` operation for FireStore (Firebase's latest DB endeavor) I came across a rather obvious sounding yet perplexing error:

```
Function CollectionReference.add() requires its first argument to be of type object, but it was: a custom object
```

It was asking me to cast my `model` into an `object` which wasn't an unreasonable thing to ask but it felt very unpolished.

Isn't the whole point of writing typed code like `private myCollection: AngularFirestoreCollection<SomeModel>` in TypeScript, about then using statements like `this.myCollection.add(someModelNewInstance);` and having them be implicitly understood?

I found some matches on StackOverflow:
* https://stackoverflow.com/questions/47110905/adding-data-to-firebase-cloud-firestore-and-angular
* https://stackoverflow.com/questions/37300338/how-can-i-convert-a-typescript-object-to-a-plain-object

When doing extra work like:
```
    this.myCollection.add({
      keyA: someModelNewInstance.keyA,
      keyB: someModelNewInstance.keyB,
    });
```
I just can't help but feel that either I don't fully understand the AngularFire library or there's room for improvement.

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUxMjI4MDgwXX0=
-->