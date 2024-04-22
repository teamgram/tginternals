# iOS & macOS SDK

TGPassportKit helps you easily integrate Telegram Passport requests into your iOS & macOS apps. Check out our GitHub repository to see samples using this SDK.

### Installation

#### Installing using Cocoapods

To install TGPassportKit via Cocoapods add the following to your Podfile:

then run pod install in your project root directory.

#### Installing using Carthage

Add the following line to your Cartfile:

then run carthage update, and you will get the latest version of TGPassportKit in your Carthage folder.

### Project Setup

#### Configure Your Info.plist

Configure your Info.plist by right-clicking it in Project Navigator, choosing Open As > Source Code and adding this snippet:
Replace {bot_id} with your value

#### Connect AppDelegate methods

Add this code to your UIApplicationDelegate implementation

If you support iOS 9 and below, also add this method:

### Usage

#### Add Telegram Passport Button

To add the Telegram Passport button, add the following code to your view controller:
Replace {bot_id}, {bot_public_key} and {request_nonce} with your values

#### ...or Implement Your Own Behavior

If you want to design a custom UI and behavior, you can invoke a Passport request like this:
Replace {bot_id}, {bot_public_key} and {request_nonce} with your values

