---
sidebar_position: 1
---

# Onboarding

Onboarding uses [introduction_screen](https://pub.dev/packages/introduction_screen). You can find a lot of examples in the documentation.

The file is located under `lib/features/onboarding/onboarding_screen.dart`

The `_getPages` function holds the pages. You can add as many as you want. 

```js
  List<PageViewModel> get _getPages {
    return [
      PageViewModel(
        title: S.current.onboarding_titlePage1,
        body: S.current.onboarding_bodyPage1,
        decoration: defaultOnboardingDecoration,
        image: const _OnboardingImage(Icons.rocket_launch),
      ),
      PageViewModel(
        title: S.current.onboarding_titlePage2,
        body: S.current.onboarding_bodyPage2,
        decoration: defaultOnboardingDecoration,
        image: const _OnboardingImage(Icons.stars_rounded),
      )
    ];
  }
```

## Reset onboarding

In the [Debug Menu](debug-menu) you can reset the Onboarding.

In the code this is done via the `storageProvider`.