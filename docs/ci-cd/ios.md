
# iOS Workflow

## Getting Started

The CI workflow is defined in `.github/workflows/ios-deploy-testflight.yml`. 

It works with Fastlane and uses the [fastlane-match](https://docs.fastlane.tools/actions/match/) action to manage the code signing certificates and provisioning profiles. You can find the Fastlane documentation [here](https://docs.fastlane.tools/).

Before you can use it, you need to set up Fastlane and add the required secrets to your GitHub repository.

Adjust the `Appfile`, `Fastfile` and `Matchfile` to your needs. You can find them in the `fastlane` folder.

### App Store Connect API Key

First you need to create an API Key in App Store Connect. You can find the documentation [here](https://developer.apple.com/documentation/appstoreconnectapi/creating_api_keys_for_app_store_connect_api).

Here are the steps
```
1. Select Users and Access, Integrations tab and then select the App Store Connect API.
2. Make sure the Team Keys tab is selected.
3. Click Generate API Key or the Add (+) button.
4. Enter a name for the key. The name is for your reference only and isn’t part of the key itself.
5. Under Access, select the role for the key.
6. Click Generate.
7. The new key’s name, key ID, a download link, and other information appears on the page.
```

### Secrets

1. `APP_STORE_CONNECT_API_KEY_ISSUER_ID`: Issuer ID on APP Store Connect API page
2. `APP_STORE_CONNECT_API_KEY_KEY`: The actual Key base64 encoded
   1.  use `cat <myfile>.p8 | base64` to get the base64 encoded key
3. `APP_STORE_CONNECT_API_KEY_KEY_ID`: Key ID in the table
4. `MATCH_PASSWORD`: The password that you set for your match repository
5. `MATCH_GIT_BASIC_AUTHORIZATION`: Create a personal access token 
   ```
   1. Go to your GitHub account settings
   2. Click on Developer settings
   3. Personal access tokens
   4. Fine-grained tokesn
   5. Choose actions and contents permissions
   6. Generate token
    ```

### Fastfile

Update the name of the app in the `Fastfile` to match your app name. I highlighted it with `TODO` comments.

### Matchfile

1. Update the `git_url` to match your repository.
2. Update the `app_identifier` to match your app identifier. 
3. Update the `username` to match your Apple ID.

I highlighted it with `TODO` comments.

### Appfile

1. Update the `app_identifier` to match your app identifier.
2. Update the `apple_id` to match your Apple ID.
3. Update the `team_id` to match your Developer Portal Team ID
4. Update the `itc_team_id` to match your App Store Connect Team ID
