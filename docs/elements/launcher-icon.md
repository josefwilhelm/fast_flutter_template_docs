# Flutter Launcher Icons

## Overview

We use [flutter_launcher_icons](https://pub.dev/packages/flutter_launcher_icons) to generate the launcher icons.

The configuration is located in `pubspec.yaml` under `flutter_icons`.

```yaml
flutter_launcher_icons:
  android: "launcher_icon"
  ios: true
  image_path: "assets/images/logo.png"
  remove_alpha_ios: true
  adaptive_icon_background: "#FFDADA"
```

Now you all need to do is run

```shell
flutter pub run flutter_launcher_icons
```

The package will update the n