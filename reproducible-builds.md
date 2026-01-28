# Reproducible Builds for iOS and Android

This page contains instructions for verifying that Telegram's open source code is exactly the same as the code that is used to build the apps that are available in the App Store, Google Play and directly on the Telegram website.

Warning: Telegram supports reproducible builds as of version 5.13. Bear in mind that, at this stage, the verification process should be considered experimental. We will be updating our apps and these instructions to make this process as straightforward as possible.

- Telegram for Android

- Telegram for iOS

> Please read the relevant notes and troubleshooting section carefully.

---

### Step 1. Install Docker

Docker can be obtained here. Once the installation is complete, log into your Docker account > Settings > Resources > Advanced and configure the amount of resources Docker may use:

We recommend using the maximum amount allowed by your system's hardware, in order to speed up the build time.

### Step 2. Confirm which version you have installed on your Android device

You can find the version/build number  and the source (website, Play Store, Huawei Store) at the bottom of the Settings page. Note that Telegram supports reproducible builds starting with version 5.13.

The commit tag to checkout source code for the example above will be release-9.3.3_3026.

> Please make sure that you're using the correct version and build number  of the version you want to check (and not the one from this example ).

### Step 3. Obtain the source code

Open Terminal, run the commands:git clone https://github.com/DrKLO/Telegram.git $HOME/telegram-androidcd $HOME/telegram-androidgit checkout release-{VERSION AND BUILD NUMBER FROM STEP 2}

For our example, the command would be:git checkout release-5.13.0_1821

### Step 4. Build the app

Open Terminal, run the commands:cd $HOME/telegram-androiddocker build -t telegram-build .

docker run --rm -v "$PWD":/home/source telegram-build

These commands will produce 3 different APKs and 2 bundles:

/apk/afat/standalone/app.apk – used for direct downloads from telegram.org/android/apk/afat/elease/app.apk – the playstore version/apk/afat/release/app-huawei.apk – used exclusively for the Huawei store

bundle/bundleAfat_SDK23Release/TMessagesProj_App-bundleAfat_SDK23-release.aabbundle/bundleAfatRelease/TMessagesProj_App-bundleAfat-release.aab

These APKs can be found in:$HOME/telegram-android/TMessagesProj/build/outputs/apk/afat/

Use the folder name from Step 4 to find the correct folder that holds the same APK as installed on your device. For example, for the Play Store version, the path to your APK will be:

$HOME/telegram-android/TMessagesProj/build/outputs/apk/afat/release/app.apkCopy this APK to the root source directory by running this command in Terminal:cp $HOME/telegram-android/TMessagesProj/build/outputs/apk/afat/release/app.apk $HOME/telegram-android/telegram_built.apk

### Step 5. The Telegram APK installed on your device

You will need adb for this step.

> If you downloaded your APK directly from Telegram's website, use the package name org.telegram.messenger.web in this step. To verify the Google Play APK, use org.telegram.messenger.

Connect your device to the computer, open Terminal, run the commands:adb shell pm path org.telegram.messenger

The output will look something like this:package:/data/app/org.telegram.messenger-_zOSURFEx2GpHM8UDF_PVg==/base.apkBy using this information, pull the APK from your device to $HOME/telegram-android using command:adb pull /data/app/org.telegram.messenger-_zOSURFEx2GpHM8UDF_PVg==/base.apk $HOME/telegram-android/telegram_store.apk

### Step 6. Compare the APKs

To compare Direct and Huawei Store versions, open Terminal, run the commands:cd $HOME/telegram-androidpython apkdiff.py telegram_store.apk telegram_built.apkIf the APKs are the same, you will seeAPKs are the same!

Play Store versions built from a bundle will be marked as 'store bundled'. To verify such builds, use:

python apkfrombundle.py  telegram_bundle.aab  telegram_store.apk

If anything goes wrong, you will see this:

If your APKs don't match, please make sure that you chose the correct code version and the right SDK.

Check out the Troubleshooting section first in case you run into trouble.

---

The verification process for iOS builds is, unfortunately, a lot more complex than for Android. The two main issues with Apple's current policies and infrastructure are as follows:

> As things stand now, you'll need a jailbroken device, at least 1,5 hours and approximately 90GB of free space to properly set up a virtual machine for the verification process.

To provide a stable and easily reproducible environment, Telegram iOS builds are compiled on a virtual machine.

### Step 1. Running Darwin-Containers

### Step 2. Creating an OS image

> Check versions.json for information on the relevant macOS and Xcode versions.

./darwin-containers fetch

Download the appropriate macOS restore image (e.g. 13.6):

./darwin-containers fetch "macOS 13.6"

Create a new OS image:

./darwin-containers create --source "macOS 13.6" --tag "macos-13.0-xcode-{XCODE_VERSION}" --manual

Follow the installation instructions. Set username to containerhost and password to containerhost.

Enable Remote Login and allow full disk access for remote users.

Connect to the guest VM using SSH with username containerhost and password containerhost.

Create the directory ~/.ssh and set up the authorized_keys using the public key string printed by the darwin-containers create command earlier.

Upload the appropriate version of Xcode via scp and install to /Applications. Run it at least once to complete installation. Don't forget to download the iOS SDK.

Shut down the guest OS.

### Step 3. Obtaining verification IPA

```
python3 -u build-system/Make/Make.py remote-build --darwinContainers="path-to-darwin-containers-script" --darwinContainersHost="unix://$HOME/.darwin-containers.sock" --configurationPath="build-system/appstore-configuration.json" --codesigningInformationPath=build-system/fake-codesigning --configuration=release_arm64
```

For more information see:

build-system/Make/RemoteBuild.py.gitlab-ci.yml lane verify_beta_testflight

### Step 4. Obtaining the source code

git clone --recursive https://github.com/TelegramMessenger/telegram-ios.git $HOME/telegram-ioscd $HOME/telegram-iosgit checkout release-${VERSION_NUMBER}

E.g., git checkout release-7.3. Please note that you need to check out the whole git history as the build version depends on the number of commits in the repository.

### Step 5. Downloading a decrypted version of the app from the App Store

This step requires a jailbroken device equipped with tools for decrypting apps. We‘d love to make this process more simple but that’s what you get for using Apple tech.

### Step 6. Comparing the AppStore build and the version built in the virtual machine

Runpython3 tools/ipadiff.py build/artifacts/Telegram.ipa PATH-TO-THE-IPA-FILE-FROM-STEP-9

In case of a successful comparison, you will get a text along these lines:

```
IPAs are equal, except for the files that can't currently be checked:
    Excluded files that couldn't be checked due to being encrypted:
        PlugIns/SiriIntents.appex/SiriIntents
        PlugIns/Widget.appex/Widget
        PlugIns/NotificationContent.appex/NotificationContent
        PlugIns/NotificationService.appex/NotificationService
        PlugIns/Share.appex/Share
    IPAs contain Watch directory with a Watch app which can't be checked currently.
    IPAs contain .car (Asset Catalog) files that are compiled by the App Store and can't currently be checked:

        Frameworks/TelegramUI.framework/Assets.car
        Assets.car
    IPAs contain .nib (compiled Interface Builder) files that are compiled by the App Store and can't currently be checked:
        Base.lproj/LaunchScreen.nib
```

In case of any mismatches, you'll get a detailed report.

---

### iOS: Notes

---

If you encounter any issues with obtaining the code, building and comparing the apps, please contact us at @BotSupport and include the hashtag #reproducibleBuilds with your message describing the problem.

### Troubleshooting: Android

bazel

mkdir -p $HOME/bazel && cd $HOME/bazelcurl -O -L https://github.com/bazelbuild/bazel/releases/download/3.7.0/bazel-3.7.0-darwin-x86_64mv bazel-3.7.0-darwin-x86_64 bazel

Check that you have downloaded the correct version:chmod +x bazel./bazel --version

### Step 7. Building the app

Open Terminal, run the commands:cd $HOME/telegram-ios
BAZEL="$HOME/bazel/bazel" sh buildbox/build-telegram.sh verify

If the environment has been set up correctly, this will start the building process. Note that this step can easily take 30-40 minutes. The average build time on a MacBook Pro (i9 6 core) is 35 minutes.

Once the process is complete the resulting IPA file can be found in build/artifacts/Telegram.ipaAll the following steps will be made via Terminal on your main system.

### Step 8. Downloading a decrypted version of the app from the App Store

This step requires a jailbroken device equipped with tools for decrypting apps. We‘d love to make this process more simple but that’s what you get for using Apple tech.

### Step 9. Comparing the AppStore build and the version built in the virtual machine

Install the necessary tools:if ! type brew > /dev/null;
 then /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"; fi && brew install python3

Runpython3 tools/ipadiff.py build/artifacts/Telegram.ipa PATH-TO-THE-IPA-FILE-FROM-STEP-9

In case of a successful comparison, you will get a text along these lines:

In case of any mismatches, you'll get a detailed report.

---

#### iOS, XCode 14

Due to compiler bugs introduced by Apple in Xcode 14 (read more), you will need to use the modified instructions below to verify the latest builds:

Remove steps 6, 7

Steps 1-4.1 are replaced with:

##### Running Darwin-Containers:

##### Creating an OS image:

./darwin-containers fetch

Download the appropriate macOS restore image (e.g. 13.0):

./darwin-containers fetch "macOS 13.0"

Create a new OS image:

./darwin-containers create --source "macOS 13.0" --tag "macos-13.0-xcode-14.1" --manual

Follow the installation instructions. Set username to containerhost and password to containerhost.Enable Remote Login and allow full disk access for remote users.Connect to the guest VM using SSH with username containerhost and password containerhost.Create directory ~/.ssh and set up the authorized_keys using the public key string printed by the darwin-containers create command earlier.Upload the appropriate version of Xcode via scp and install to /Applications. Run it at least once to complete installation.Shutdown the guest OS.

##### Obtaining verification IPA:

python3 -u build-system/Make/Make.py remote-build --darwinContainers="path-to-darwin-containers-script" --darwinContainersHost="unix://$HOME/.darwin-containers.sock" --configurationPath="build-system/appstore-configuration.json" --codesigningInformationPath=build-system/fake-codesigning --configuration=release_arm64

For more information see:

build-system/Make/RemoteBuild.py.gitlab-ci.yml lane verify_beta_testflight

---

### iOS: Notes

---

If you encounter any issues with obtaining the code, building and comparing the apps, please contact us at @BotSupport and include the hashtag #reproducibleBuilds with your message describing the problem.

### Troubleshooting: Android

### Troubleshooting: iOS

> UPD: Despite the fact that the issue below persists, we were able to restore deterministic builds using manually crafted linker flags. See these updated steps for XCode 14.

Due to recent changes introduced in XCode 14 by Apple, it is currently not possible to create reproducible builds for iOS using tools officially supported by Apple. We will update this page as soon as Apple resolves the issue.

To confirm the issue for yourself, follow these steps:

- With some probability, the ordering of the LC_LOAD_DYLIB commands will vary.

- The __LIKEDIT section will always vary.

