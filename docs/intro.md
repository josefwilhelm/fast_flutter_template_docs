---
slug: /
sidebar_position: 1
---

# Getting started

:::info
As this template is for developers, I assume you already have Flutter installed. If not, you can find the installation instructions [here](https://flutter.dev/docs/get-started/install).
:::

## Introduction

Hey there,
Thanks for using my template. I hope it will help you to build your app faster. But no more talking, let's get started.

### First, you need to clone the repo. 

```bash
git clone git@github.com:josefwilhelm/fast_flutter_template.git [YOUR_APP_NAME]
cd [YOUR_APP_NAME]
```

### Flutter version

:::info

This template is built and tested with Flutter **3.16.0. **

:::


I recommend using fvm to manage your Flutter versions. You can find more information [here](elements/fvm.md).

### Quick start

1. Fetch the dependencies with `flutter pub get`.
2. Then we need to set up Firebase. Follow the instructions [here](/firebase/firebase-setup).
   
:::info
ATTENTION: You have to enable Firebase Functions and Firebase Firestore in order to use the authentication properly. 
Make sure you set up Firebase Functions before you continue. You can find the instructions [here](/firebase/firebase-setup).
:::


### Now we can run the app. 

```bash
flutter run
```

:::tip

Congrats, your app will now run on your device or emulator.

:::

---

## Some more infos

### Some code is generated using build runner.

Here is the documentation for [build runner](https://pub.dev/packages/build_runner)


If you add new models or providers you need to run the following command:

    flutter pub run build_runner build --delete-conflicting-outputs

### Project structure:

    
I use a `feature first` folder structure. 

For example the dashboard feature is located in `lib/features/dashboard`.

Within this folder you will find the following folders:

- `views` - contains the UI
- `providers` - contains the providers
- `models` - contains the models

`lib/common` contains code that is shared across the app. For example the `widget` folder contains the nav bar and a primary button. 

```
lib
├── common
│   ├── extensions
│   ├── widgets
│   ├── providers
│   └── widgets
├── features       
│   ├── authentication
│   ├── dashboard
│       ├── models
│       ├── providers
│       └── views
│   ├── onboarding
│   ├── settings
├── i10n
├── generated
├── main.dart
```

:::tip
You will find a `NOTE` comments in the source code. These are sections where you have to fill in API keys or similiar.
:::


### What's included

- Riverpod
- Dark Mode
- Rate my app
- Settings UI
- Firebase setup
- Material Theme
- Authentication
- Code generation
- Bottom Navigation
- Logger & Provider Logger
- Navigation with auto_route

