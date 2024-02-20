# Rate my app

This is such an important feature. You want the support of your users if you want your app to succeed. 

I use the [rate_my_app](https://pub.dev/packages/rate_my_app) package to ask the user to rate the app.

In `lib/common/providers/rate_my_app_provider.dart` you will find the provider for the `RateMyApp` package.

There you can specify the conditions when the dialog should be shown. 



In the `app.dart` file you can find the following code which initializes the `RateMyApp` package:


`ref.read(rateMyAppProvider);`

:::tip

Show the dialog after the user has used the app for a few days or if the user did something for the first time. In the case of a meditation app, you could show the dialog after the user has meditated for the first time.

:::
