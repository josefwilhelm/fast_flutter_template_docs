---
sidebar_position: 2
---

# Firebase Analytics

## Getting Started

In order to use Firebase Analytics, you need to enable it in your Firebase project. You can do this by going to the [Firebase Console](https://console.firebase.google.com/), selecting your project, and then clicking on the "Analytics" tab in the left sidebar. From there, you can click the "Enable Analytics" button to enable it.

No more setup is required. You can now use Firebase Analytics in your app.

## Usage

Here you can see that after the login, the event is send to Firebase. 
More info [here](https://firebase.google.com/docs/analytics/get-started?platform=flutter)

```js title=lib/features/authentication/providers/auth_provider.dart
  Future<void> signInWithEmailAndPassword(String email, String password) async {
    state = const AsyncValue.loading();
    try {
      state = await AsyncValue.guard(() async {
        final user = await ref
            .read(firebaseAuthRepositoryProvider)
            .signIn(email, password);

        //Log analytics event
        ref.read(analyticsProvider).logEvent(name: 'Login');
        return user;
      });
    } catch (e, s) {
      state = AsyncValue.error(e, s);
    }
  }

```