# Getting Started

In order to use Firebase with your app we need to setup a few things. 

You can find the whole documentation [here](https://firebase.google.com/docs/flutter/setup?platform=ios)

1. We need a Firebase account and call 
```
firebase login
````

2. As we will use the Firebase CLI to set up a lot things we need to install it 
```
dart pub global activate flutterfire_cli
```

3. Now we can connect our project with Firebase 
```
flutterfire configure
```

4. Now you can create a new project or use an existing one. The following picture shows how it's done with a new project. 

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

5. If we now have a look at the [Console](https://console.firebase.google.com/u/3/) we will find the project there. 

![Firebase Console](assets/firebase-console.png)


--- 


This is all the set up we need to let our app run. 