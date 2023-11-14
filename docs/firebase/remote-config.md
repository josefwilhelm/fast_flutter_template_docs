# Remote Config

## Overview

Remote Config is a cloud service that lets you change the behavior and appearance of your app without requiring users to download an app update. When using Remote Config, you create in-app default values that control the behavior and appearance of your app. Then, you can later use the Firebase console or the Remote Config backend APIs to override in-app default values for all app users or for segments of your user base. Your app controls when updates are applied, and it can frequently check for updates and apply them with a negligible impact on performance.

You can find the provider file under `lib/common/providers/fireabse/remote_config_provider.dart`.

For now the only value that is set is the `showOnboarding` value. This is used to determine if the user should see the onboarding or not.

```js title=lib/common/providers/fireabse/remote_config_provider.dart
@Riverpod(keepAlive: true)
RemoteConfigService remoteConfig(RemoteConfigRef ref) {
  return RemoteConfigService();
}

class RemoteConfigService {
  final remoteConfig = FirebaseRemoteConfig.instance;

  RemoteConfigService() {
    init();
  }

  Future<void> init() async {
    await remoteConfig.setConfigSettings(RemoteConfigSettings(
      fetchTimeout: const Duration(minutes: 1),
      minimumFetchInterval:
          kDebugMode ? Duration.zero : const Duration(hours: 1),
    ));

    await remoteConfig.setDefaults(<String, dynamic>{
      'showOnboarding': true,
    });

    await remoteConfig.fetchAndActivate();
  }

  bool get showOnboarding => remoteConfig.getBool('showOnboarding');
}
```