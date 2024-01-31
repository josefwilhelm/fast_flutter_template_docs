# Android Workflow

Jobs
The workflow contains a single job android_build_release which is responsible for building and deploying the Android application.

Deploy
Steps
The job consists of several steps:

Checkout the code: This step checks out your repository so the workflow can access it.

Setup Flutter: This step sets up Flutter using the Flutter Version Manager (FVM) and the subosito/flutter-action action.

Setup Ruby: This step sets up Ruby, which is required to run Fastlane.

Create key.properties: This step creates the key.properties file required for signing your Android application.

Create key.jks: This step creates the key.jks file from a base64 encoded string. This file is also required for signing your Android application.

Build the app: This step runs flutter pub get to get the dependencies and flutter build appbundle to build the Android application.

Deploy the app: This step installs the required Ruby gems and runs the Fastlane lane android_internal to deploy the Android application.

Secrets
The workflow uses several secrets to sign the Android application. You need to add these secrets to your GitHub repository:

KEYSTORE_STORE_PASSWORD: The password for your keystore.
KEYSTORE_KEY_PASSWORD: The password for your key.
KEYSTORE_KEY_ALIAS: The alias of your key.
KEYSTORE_KEY_JKS: The base64 encoded string of your key.jks file.
You can add these secrets in the Settings tab of your GitHub repository, under Secrets.

Conclusion
This workflow allows you to automate the process of building and deploying your Android application whenever you push to the r branch. Make sure to replace the placeholders with your actual values.


| Testing Method | Pros | Cons |
|---|---|---|
| Golden testing | Easy to set up, reliable, thorough, maintainable | May be brittle, requires manual setup |
| Widget tests | Easy to write and maintain | Can be brittle |
| Unit tests | Robust | More difficult to write |
| End-to-end tests | Comprehensive testing, simulates user interaction | Slow, difficult to write |
