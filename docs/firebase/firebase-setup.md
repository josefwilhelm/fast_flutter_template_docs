---
sidebar_position: 1
---

# Firebase setup

<!-- :::info
You need a Firebase account to use Firebase. You can create one [here](https://console.firebase.google.com/u/3/).
::: -->

In order to use Firebase with your app we need to setup a few things. 
You can find the whole documentation [here](https://firebase.google.com/docs/flutter/setup?platform=ios)

:::info
A few steps are required to set up Firebase.
1. Create an account
2. Create a new project
3. Add your app to the project
4. Enable billing in order to use Firebase Functions (you will still be in the free tier, but Functions won't work otherwise)
5. Enable Firebase Functions and Firestore
6. Deploy the functions and firestore rules
::: 

## The steps in detail

### 1. Create an account
- Just go to the [Firebase Console](https://console.firebase.google.com/)

### 2. Create a new project

- Follow the instructions [here](https://firebase.google.com/docs/cli#setup_update_cli)
- Or do it in the next step with the Firebase CLI

### 3. Add your app to the project

1. Install the Firebase CLI. Follow the instructions [here](https://firebase.google.com/docs/flutter/setup?platform=ios)
2. **Important** Adjust your app identifiers in `ios/Runner.xcodeproj/project.pbxproj` and `android/app/build.gradle` before you continue.
3. Run `flutterfire configure` in your project directory. You can create a new project or use an existing one. The following picture shows how it's done with a new project. This step will add the apps to your Firebase project with the app identifiers you set in the previous step.

```shell
user@users-macbook fast_flutter_template % flutterfire configure
i Found 8 Firebase projects.                                                                                                                                                                                                                                                        
✔ Select a Firebase project to configure your Flutter application with · <create a new project>                                                                                                                                                                                     
✔ Enter a project id for your new Firebase project (e.g. my-cool-project) · best-meditation-app-2023                                                                                                                                                                                
i New Firebase project best-meditation-app-2023 created successfully.                                                                                                                                                                                                               
✔ Which platforms should your configuration support (use arrow keys & space to select)? · android, ios, web                                                                                                                                                                         
i Firebase android app com.example.fast_flutter_template is not registered on Firebase project best-meditation-app-2023.                                                                                                                                                            
i Registered a new Firebase android app on Firebase project best-meditation-app-2023.                                                                                                                                                                                               
i Firebase ios app com.example.fastFlutterTemplate is not registered on Firebase project best-meditation-app-2023.                                                                                                                                                                  
i Registered a new Firebase ios app on Firebase project best-meditation-app-2023.                                                                                                                                                                                                   
i Firebase web app fast_flutter_template (web) is not registered on Firebase project best-meditation-app-2023.                                                                                                                                                                      
i Registered a new Firebase web app on Firebase project best-meditation-app-2023.                                                                                                                                                                                                   
✔ The files android/build.gradle & android/app/build.gradle will be updated to apply Firebase configuration and gradle build plugins. Do you want to continue? · yes                                                                                                                                                                                                         

```

1. We need to login to our Firebase account.

```
firebase login
````

3. As we will use the Firebase CLI to set up a lot things we need to install it 


```
dart pub global activate flutterfire_cli
```

:::info
Adjust your app identifiers in `ios/Runner.xcodeproj/project.pbxproj` and `android/app/build.gradle` before you continue.
:::

1. Now we can connect our project with Firebase 
```
flutterfire configure
```

1. Now you can create a new project or use an existing one. The following picture shows how it's done with a new project. 

```shell
user@users-macbook fast_flutter_template % flutterfire configu
i Found 8 Firebase projects.                                                                                                                                                                                                                                                        
✔ Select a Firebase project to configure your Flutter application with · <create a new project>                                                                                                                                                                                     
✔ Enter a project id for your new Firebase project (e.g. my-cool-project) · best-meditation-app-2023                                                                                                                                                                                
i New Firebase project best-meditation-app-2023 created successfully.                                                                                                                                                                                                               
✔ Which platforms should your configuration support (use arrow keys & space to select)? · android, ios, web                                                                                                                                                                         
i Firebase android app com.example.fast_flutter_template is not registered on Firebase project best-meditation-app-2023.                                                                                                                                                            
i Registered a new Firebase android app on Firebase project best-meditation-app-2023.                                                                                                                                                                                               
i Firebase ios app com.example.fastFlutterTemplate is not registered on Firebase project best-meditation-app-2023.                                                                                                                                                                  
i Registered a new Firebase ios app on Firebase project best-meditation-app-2023.                                                                                                                                                                                                   
i Firebase web app fast_flutter_template (web) is not registered on Firebase project best-meditation-app-2023.                                                                                                                                                                      
i Registered a new Firebase web app on Firebase project best-meditation-app-2023.                                                                                                                                                                                                   
✔ The files android/build.gradle & android/app/build.gradle will be updated to apply Firebase configuration and gradle build plugins. Do you want to continue? · yes                                                                                                                                                                                                         

```

### 4. Enable billing
1. Go to the [Firebase Console](https://console.firebase.google.com/u/3/)
2. Select your project
3. Go to `Project settings`
4. Go to `Usage and billing`
5. Enable billing (Blaze plan)


### 5. Enable Firebase Functions and Firestore
1. Run `firebase init` in your project directory
2. Select `Functions` and `Firestore` and select your project 
3. Follow the instructions in command line.
   1. For Functions: See the settings to select below. 
   2. For Firestore: Choose the default settings.
4. Go to the Firebase Console and check if Functions and Firestore are enabled.
5. If we now have a look at the [Console](https://console.firebase.google.com/u/3/) we will find the project there. 

Functions settings:

```shell
=== Functions Setup

Detected existing codebase(s): default

? Would you like to initialize a new codebase, or overwrite an existing one? Overwrite

Overwriting codebase default...

? What language would you like to use to write Cloud Functions? TypeScript
? Do you want to use ESLint to catch probable bugs and enforce style? Yes
? File functions/package.json already exists. Overwrite? No
i  Skipping write of functions/package.json
? File functions/.eslintrc.js already exists. Overwrite? No
i  Skipping write of functions/.eslintrc.js
? File functions/tsconfig.json already exists. Overwrite? No
i  Skipping write of functions/tsconfig.json
? File functions/tsconfig.dev.json already exists. Overwrite? No
i  Skipping write of functions/tsconfig.dev.json
? File functions/src/index.ts already exists. Overwrite? No
i  Skipping write of functions/src/index.ts
? File functions/.gitignore already exists. Overwrite? No
i  Skipping write of functions/.gitignore
? Do you want to install dependencies with npm now? Yes

```



### 6. Deploy the functions and firestore rules

1. Run `firebase deploy` in your project directory






