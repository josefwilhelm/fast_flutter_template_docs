# State-management


## Riverpod

This project uses Riverpod v2 for state management.

Here is the documentation for Riverpod: [Riverpod](https://riverpod.dev/)

I wrote here about why I use Riverpod. 
https://josef-wilhelm.beehiiv.com/p/why-i-use-riverpod-as-state-management

### Invalidating Providers on Logout

Make sure to invalidate all providers that depend on the user state when the user signs out.
You can do this by calling `ref.invalidate()` on the provider.

Do this in the `logout` method in the `lib/features/authentication/providers/auth_provider.dart` file.


### Logging

Logging is enabled in debug mode.
Just comment out the `ProviderLogger` if you don't want to see logs.
In the `main.dart` file you can find the following code:

```dart
runApp(
    ProviderScope(
      observers: [
        if (kDebugMode) //NOTE: Remove this is you don't want to see logs
          ProviderLogger(),
      ],
      child: const App(),
    ),
  );
```