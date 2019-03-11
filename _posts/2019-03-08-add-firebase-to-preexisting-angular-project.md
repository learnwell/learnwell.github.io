---

layout: postMod1
title: How to add firebase to a preexisting angular project?
author: pulkit
last_modified_at: March 08, 2019
tags: [angular,firebase]

---

1. Navigate to your pre-existing angular project

    ```
    $ cd ~/dev && git clone https://github.com/<username>/my-project my-project
    $ cd ~/dev/my-project
    ```
1. Install the Firebase CLI

    ```
    $ npm -g install firebase-tools
    $ firebase --version
    $ firebase login
    ```
1. Initialize firebase configuration for your pre-existing angular project

    ```
    $ cd ~/dev/my-project && \
      firebase init

    ? Which Firebase CLI features do you want to setup for this folder? Press Space to select features, then Enter to confirm your choices. 
     ◯ Database: Deploy Firebase Realtime Database Rules
     ◉ Firestore: Deploy rules and create indexes for Firestore
     ◯ Functions: Configure and deploy Cloud Functions
    ❯◉ Hosting: Configure and deploy Firebase Hosting sites
     ◯ Storage: Deploy Cloud Storage security rules

    ? What file should be used for Firestore Rules? firestore.rules
    ? What file should be used for Firestore indexes? firestore.indexes.json
    ? What do you want to use as your public directory? dist/upkeep-front
    ? Configure as a single-page app (rewrite all urls to /index.html)? No
    ✔  Wrote dist/upkeep-front/404.html

    ? File dist/upkeep-front/index.html already exists. Overwrite? No
    i  Skipping write of dist/upkeep-front/index.html

    i  Writing configuration info to firebase.json...
    i  Writing project information to .firebaserc...

    ✔  Firebase initialization complete!
    ```
    > NOTE: It is _**SUPER**_ important to point `public directory` accurately to wherever your prod build will dump its data, like I did to `dist/upkeep-front` in the step above.
1. Install dependencies for firebase locally in your pre-existing angular project

    ```
    $ cd ~/dev/upkeep-front
    $ npm install --save-exact firebase
    $ npm install --save-exact @angular/fire
    % npm install --save-exact @types/firebase
    ```
1. Setup `src/app/environments/environment.ts` file in your Angular project with a firebaseConfig object and insert the relevant details from your firebase project.

    ```
    export const environment = {
      production: false,
      firebaseConfig : {
        apiKey: "YOUR_API_KEY",
        authDomain: "YOUR_AUTH_DOMAIN",
        databaseURL: "YOUR_DATABASE_URL",
        projectId: "YOUR_PROJECT_ID",
        storageBucket: "YOUR_STORAGE_BUCKET",
        messagingSenderId: "YOUR_MESSAGING_SENDER_ID"
      }
    };
    ```
1. Load [relevant firebase modules](https://github.com/angular/angularfire2/blob/master/docs/install-and-setup.md#6-setup-individual-ngmodules) into Angular. Open the `src/app/app.module.ts` file and update it accordingly:

    ```
    import { AngularFireModule } from '@angular/fire';
    import { AngularFirestoreModule } from '@angular/fire/firestore';
    import { environment } from '../environments/environment';

    @NgModule({
            // [...]
        imports: [
            // [...]
            AngularFireModule.initializeApp(environment.firebaseConfig),
            AngularFirestoreModule
        ],
    ```
1. Build and deploy locally

    ```
    ng build --prod
    firebase serve --only hosting
    ```
1. Setup `src/app/environments/environment.prod.ts` file (NOTICE: this is `prod.ts`, itsdifferent from the one before) in your Angular project with a firebaseConfig object and insert the relevant details from your firebase project.

    ```
    export const environment = {
      production: true,
      firebaseConfig : {
        apiKey: "YOUR_API_KEY",
        authDomain: "YOUR_AUTH_DOMAIN",
        databaseURL: "YOUR_DATABASE_URL",
        projectId: "YOUR_PROJECT_ID",
        storageBucket: "YOUR_STORAGE_BUCKET",
        messagingSenderId: "YOUR_MESSAGING_SENDER_ID"
      }
    };
    ```
1. Build and deploy to the world

    ```
    ng build --prod
    firebase deploy
    ```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ3MjAwODkyOF19
-->