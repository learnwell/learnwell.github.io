---

layout: postMod1
title: How to extract data from AngularFire Observables?
author: pulkit
last_modified_at: March 09, 2019
tags: [firestore,firebase,angularfire]

---

## Step by Step

1. Update your model(s) to have an additional `id` property, in addition to everything else that your business logic dictates.

    ```
    export class SomeModel {
        public id?: string; 
    }
    ```
1. Setup a service to fetch data

    ```
    import {
    AngularFirestore,
    AngularFirestoreCollection } from '@angular/fire/firestore';

    export class MyService {
        private myCollection: AngularFirestoreCollection<any>;
        private data: SomeModel[];

        constructor(private ngFirestore: AngularFirestore) {
            this.myCollection = this.ngFirestore.collection<SomeModel>('questions');
        }

        async getData(): Promise<SomeModel[]> {
            return await new Promise((resolve, reject) => {
                this.myCollection.snapshotChanges().subscribe(data => {
                    this.data = data.map(e => {
                      return {
                        id: e.payload.doc.id,
                        ...e.payload.doc.data()
                      };
                    });
                    resolve(this.data);
                });
            });
        }
    }
    ```
1. Add your service to your `AppModule` as a `provider`

    ```
    @NgModule({
      ...
      providers: [
        MyService
      ]
    })
    export class AppModule {}
    ```
1. [Optional] Load the data from service into a component

    ```
    @Component({
        templateUrl: './my.component.html',
        styleUrls: ['./my.component.scss']
    })
    export class MyComponent implements OnInit {
        public data: SomeModel[] = [];
        constructor(private readonly myService: MyService) {}
        async ngOnInit() {
            this.data = await this.myService.getData();
        }
    }
    ```

## References

* StackOverflow Post: [How can we access a non-observable dataset from Firebase's Firestore?](https://stackoverflow.com/questions/55093849/how-can-we-access-a-non-observable-dataset-from-firebases-firestore)

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM0MTEwMTY4MV19
-->