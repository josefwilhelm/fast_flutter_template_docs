# Intl - Translations

## Overview

For translations I use the Flutter intl extension. 

You can download it for VS Code [here](https://marketplace.visualstudio.com/items?itemName=localizely.flutter-intl) and for Android Studio [here](https://plugins.jetbrains.com/plugin/13666-flutter-intl).


### Setup

The app is already setup to use translations. 
You can check that in the `pubspec.yaml` file. 

```yaml
flutter_intl:
  enabled: true
  ```

### Usage

You can add a language by running the following command `Flutter Intl: Add locale`.

This will create a new `.arb`file in the `lib/l10n` folder.

The app is set-up for `English` and `German`.

### iOS

For iOS you need to add the following to your `Info.plist` file.

```xml
<key>CFBundleLocalizations</key>
<array>
    <string>en</string>
    <string>de</string>
</array>
```

