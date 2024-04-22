# Android SDK
The Android SDK helps you easily integrate Telegram Passport requests into your Android-based apps. Check out our GitHub repository to see samples using this SDK.
### Installation
#### Installing from Maven
Telegram Passport SDK is available from the Maven repository.
Add this line to the dependencies section in your build.gradle:
and sync your project.
#### Adding as a module
Download the library, unzip it and copy the library project to the root of your project directory (the one with settings.gradle and gradle.properties). Then, make the following changes to your Gradle scripts.
In settings.gradle, add ':telegrampassport' to includes:
In the build.gradle file for your app, add this line to the dependencies section:
and sync your project.
### Usage
#### Adding the button
The SDK provides the "Log in with Telegram" button which we recommend using for a consistent user experience across different apps. You can either add it from your Java code:
Or from XML:
#### Requesting authorization
The button doesn't do anything by itself; you need to set an OnClickListener on it to start the authorization flow (replace the comments with actual parameters):
If you need more control over the process, the TelegramPassport class contains several more methods:
- getAuthIntent(AuthParams) returns an Intent for you to use in startActivityForResult if you need to do that in some special way. Be sure to check that an app is present that can handle this intent before starting it by using PackageManager or intent.resolveActivity.
- showAppInstallAlert(Activity) shows an alert that the user needs to install Telegram in order to continue. This is intended to be used together with the previous method for the cases when the app isn't installed.
#### Handling the result
The result is delivered via the onActivityResult method in your activity with the request code you passed to TelegramPassport.request. Currently, the only meaningful parameter is resultCode, which is RESULT_OK if the authorization was successful and RESULT_CANCELED otherwise.
