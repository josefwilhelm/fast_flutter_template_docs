# Authentication

You can find the files under `lib/features/authentication/`.

## Authentication

Authentication uses [firebase_auth](https://pub.dev/packages/firebase_auth). You can find a lot of examples in the documentation.

### Errorhandling

All common errors are handled in `lib/features/authentication/providers/firebase_auth_repository.dart`.

In this file you can define more Exceptions if you want to handle more specific errors. For now these cases are handled: 

```js title="lib/features/authentication/providers/firebase_auth_repository.dart"
sealed class AuthException implements Exception {}

class WeakPasswordException extends AuthException {}

class EmailAlreadyInUseException extends AuthException {}

class TooManyRequestsException extends AuthException {}

class InvalidCredentialsException extends AuthException {}
```

The login and register screen show a `Snackbar` on Error. 
This is done via the `ref.listen` callback from Riverpod. Find more infos [here](https://riverpod.dev/docs/essentials/combining_requests#the-reflistenlistenself-methods)