# iOS Workflow

## Getting Started

The CI workflow is defined in `.github/workflows/ios-deploy-testflight.yml`. 

It works with Fastlane and uses the [fastlane-match](https://docs.fastlane.tools/actions/match/) action to manage the code signing certificates and provisioning profiles. You can find the Fastlane documentation [here](https://docs.fastlane.tools/).

Before you can use it, you need to set up Fastlane and add the required secrets to your GitHub repository.

Adjust the `Appfile`, `Fastfile` and `Matchfile` to your needs. You can find them in the `fastlane` folder.

