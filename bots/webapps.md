# Telegram Mini Apps
With Mini Apps developers can use JavaScript to create infinitely flexible interfaces that can be launched right inside Telegram — and can completely replace any website.
Like bots, Mini Apps support seamless authorization, integrated payments via 20 payment providers (with Google Pay and Apple Pay out of the box), delivering tailored push notifications to users, and much more.
> To see a Mini App in action, try our sample @DurgerKingBot.
---
### Recent changes
#### March 31, 2024
Bot API 7.2
- Added the field BiometricManager to the class WebApp.
#### December 29, 2023
Bot API 7.0
- Added the field SettingsButton to the class WebApp.
- Added the fields header_bg_color, accent_text_color, section_bg_color, section_header_text_color, subtitle_text_color, destructive_text_color to the class ThemeParams.
- Mini Apps no longer close when the method WebApp.openTelegramLink is called.
#### September 22, 2023
Bot API 6.9
- Added the field CloudStorage to the class WebApp.
- Added the methods requestWriteAccess and requestContact to the class WebApp.
- Added the fields added_to_attachment_menu and allows_write_to_pm to the class WebAppUser.
- Added the events writeAccessRequested and contactRequested.
- Added the ability to set any header color using the setHeaderColor method.
#### April 21, 2023
Bot API 6.7
- Added support for launching Mini Apps from inline query results and from a direct link.
- Added the method switchInlineQuery to the class WebApp.
#### December 30, 2022
Bot API 6.4
- Added the field platform, the optional parameter options to the method openLink and the methods showScanQrPopup, closeScanQrPopup, readTextFromClipboard to the class WebApp.
- Added the events qrTextReceived, clipboardTextReceived.
#### August 12, 2022
Bot API 6.2
- Added the field isClosingConfirmationEnabled and the methods enableClosingConfirmation, disableClosingConfirmation, showPopup, showAlert, showConfirm to the class WebApp.
- Added the field is_premium to the class WebAppUser.
- Added the event popupClosed.
#### June 20, 2022
Bot API 6.1
- Added the ability to use bots added to the attachment menu in group, supergroup and channel chats.
- Added support for t.me links that can be used to select the chat in which the attachment menu with the bot will be opened.
- Added the fields version, headerColor, backgroundColor, BackButton, HapticFeedback and the methods isVersionAtLeast, setHeaderColor, setBackgroundColor, openLink, openTelegramLink, openInvoice to the class WebApp.
- Added the field secondary_bg_color to the class ThemeParams.
- Added the method offClick to the class MainButton.
- Added the fields chat, can_send_after to the class WebAppInitData.
- Added the events backButtonClicked, settingsButtonClicked, invoiceClosed.
---
### Designing Mini Apps
#### Color Schemes
Mini Apps always receive data about the user's current color theme in real time, so you can adjust the appearance of your interfaces to match it. For example, when users switch between Day and Night modes or use various custom themes.
> Jump to technical information
#### Design Guidelines
Telegram apps are known for being snappy, smooth and following a consistent cross-platform design. Your Mini App should ideally reflect these principles.
- All elements should be responsive and designed with a mobile-first approach.
- Interactive elements should mimic the style, behavior and intent of UI components that already exist.
- All included animations should be smooth, ideally 60fps.
- All inputs and images should contain labels for accessibility purposes.
- The app should deliver a seamless experience by monitoring the dynamic theme-based colors provided by the API and using them accordingly.
---
### Implementing Mini Apps
Telegram currently supports six different ways of launching Mini Apps: from a keyboard button, from an inline button, from the bot menu button, via inline mode, from a direct link – and even from the attachment menu.
#### Keyboard Button Mini Apps
> TL;DR: Mini Apps launched from a web_app type keyboard button can send data back to the bot in a service message using Telegram.WebApp.sendData. This makes it possible for the bot to produce a response without communicating with any external servers.
Users can interact with bots using custom keyboards, buttons under bot messages, as well as by sending freeform text messages or any of the attachment types supported by Telegram: photos and videos, files, locations, contacts and polls. For even more flexibility, bots can utilize the full power of HTML5 to create user-friendly input interfaces.
You can send a web_app type KeyboardButton that opens a Mini App from the specified URL.
To transmit data from the user back to the bot, the Mini App can call the Telegram.WebApp.sendData method. Data will be transmitted to the bot as a String in a service message. The bot can continue communicating with the user after receiving it.
Good for:
- Сustom data input interfaces (a personalized calendar for selecting dates; selecting data from a list with advanced search options; a randomizer that lets the user “spin a wheel” and chooses one of the available options, etc.)
- Reusable components that do not depend on a particular bot.
#### Inline Button Mini Apps
> TL;DR: For more interactive Mini Apps like @DurgerKingBot, use a web_app type Inline KeyboardButton, which gets basic user information and can be used to send a message on behalf of the user to the chat with the bot.
If receiving text data alone is insufficient or you need a more advanced and personalized interface, you can open a Mini App using a web_app type Inline KeyboardButton.
From the button, a Mini App will open with the URL specified in the button. In addition to the user's theme settings, it will receive basic user information (ID, name, username, language_code) and a unique identifier for the session, query_id, which allows messages on behalf of the user to be sent back to the bot.
The bot can call the Bot API method answerWebAppQuery to send an inline message from the user back to the bot and close the Mini App. After receiving the message, the bot can continue communicating with the user.
Good for:
- Fully-fledged web services and integrations of any kind.
- The use cases are effectively unlimited.
#### Launching Mini Apps from the Menu Button
> TL;DR: Mini Apps can be launched from a customized menu button. This simply offers a quicker way to access the app and is otherwise identical to launching a mini app from an inline button.
By default, chats with bots always show a convenient menu button that provides quick access to all listed commands. With Bot API 6.0, this button can be used to launch a Mini App instead.
To configure the menu button, you must specify the text it should show and the Mini App URL. There are two ways to set these parameters:
- To customize the button for all users, use @BotFather (the /setmenubutton command or Bot Settings > Menu Button).
- To customize the button for both all users and specific users, use the setChatMenuButton method in the Bot API. For example, change the button text according to the user's language, or show links to different Mini Apps based on a user's settings in your bot.
Apart from this, Mini Apps opened via the menu button work in the exact same way as when using inline buttons.
> @DurgerKingBot allows launching its Mini App both from an inline button and from the menu button.
#### Inline Mode Mini Apps
> TL;DR: Mini Apps launched via web_app type InlineQueryResultsButton can be used anywhere in inline mode. Users can create content in a web interface and then seamlessly send it to the current chat via inline mode.
You can use the button parameter in the answerInlineQuery method to display a special 'Switch to Mini App' button either above or in place of the inline results. This button will open a Mini App from the specified URL. Once done, you can call the Telegram.WebApp.switchInlineQuery method to send the user back to inline mode.
Inline Mini Apps have no access to the chat – they can't read messages or send new ones on behalf of the user. To send messages, the user must be redirected to inline mode and actively pick a result.
Good for:
- Fully-fledged web services and integrations in inline mode.
#### Direct Link Mini Apps
> TL;DR: Mini App Bots can be launched from a direct link in any chat. They support a startapp parameter and are aware of the current chat context.
You can use direct links to open a Mini App directly in the current chat. If a non-empty startapp parameter is included in the link, it will be passed to the Mini App in the start_param field and in the GET parameter tgWebAppStartParam.
In this mode, Mini Apps can use the chat_type and chat_instance parameters to keep track of the current chat context. This introduces support for concurrent and shared usage by multiple chat members – to create live whiteboards, group orders, multiplayer games and similar apps.
Mini Apps opened from a direct link have no access to the chat – they can't read messages or send new ones on behalf of the user. To send messages, the user must be redirected to inline mode and actively pick a result.
Examples
https://t.me/botusername/appnamehttps://t.me/botusername/appname?startapp=command
Good for:
- Fully-fledged web services and integrations that any user can open in one tap.
- Cooperative, multiplayer or teamwork-oriented services within a chat context.
- The use cases are effectively unlimited.
#### Launching Mini Apps from the Attachment Menu
> TL;DR: Mini App Bots can request to be added directly to a user's attachment menu, allowing them to be quickly launched from any chat. To try this mode, open this attachment menu link for @DurgerKingBot, then use the  menu in any type of chat.
Mini App Bots can request to be added directly to a user's attachment menu, allowing them to be quickly launched from any type of chat. You can configure in which types of chats your mini app can be started from the attachment menu (private, groups, supergroups or channels).
Attachment menu integration is currently only available for major advertisers on the Telegram Ad Platform. However, all bots can use it in the test server environment.
To enable this feature for your bot, open @BotFather from an account on the test server and send the /setattach command – or go to Bot Settings > Configure Attachment Menu. Then specify the URL that will be opened to launch the bot's Mini App via its icon in the attachment menu.
You can add a 'Settings' item to the context menu of your Mini App using @BotFather. When users select this option from the menu, your bot will receive a settingsButtonClicked event.
In addition to the user's theme settings, the bot will receive basic user information (ID, name, username, language_code, photo), as well as public info about the chat partner (ID, name, username, photo) or the chat info (ID, type, title, username, photo) and a unique identifier for the web view session query_id, which allows messages of any type to be sent to the chat on behalf of the user that opened the bot.
The bot can call the Bot API method answerWebAppQuery, which sends an inline message from the user via the bot to the chat where it was launched and closes the Mini App.
> You can read more about adding bots to the attachment menu here.
---
### Initializing Mini Apps
To connect your Mini App to the Telegram client, place the script telegram-web-app.js in the <head> tag before any other scripts, using this code:
Once the script is connected, a window.Telegram.WebApp object will become available with the following fields:
#### ThemeParams
Mini Apps can adjust the appearance of the interface to match the Telegram user's app in real time. This object contains the user's current theme settings:
#### PopupParams
This object describes the native popup.
#### ScanQrPopupParams
This object describes the native popup for scanning QR codes.
#### PopupButton
This object describes the native popup button.
#### BackButton
This object controls the back button, which can be displayed in the header of the Mini App in the Telegram interface.
All these methods return the BackButton object so they can be chained.
#### MainButton
This object controls the main button, which is displayed at the bottom of the Mini App in the Telegram interface.
All these methods return the MainButton object so they can be chained.
#### SettingsButton
This object controls the Settings item in the context menu of the Mini App in the Telegram interface.
All these methods return the SettingsButton object so they can be chained.
#### HapticFeedback
This object controls haptic feedback.
All these methods return the HapticFeedback object so they can be chained.
#### CloudStorage
This object controls the cloud storage. Each bot can store up to 1024 items per user in the cloud storage.
All these methods return the CloudStorage object, so they can be chained.
#### BiometricManager
NEW This object controls biometrics on the device. Before the first use of this object, it needs to be initialized using the init method.
All these methods return the BiometricManager object so they can be chained.
#### BiometricRequestAccessParams
This object describes the native popup for requesting permission to use biometrics.
#### BiometricAuthenticateParams
This object describes the native popup for authenticating the user using biometrics.
#### WebAppInitData
This object contains data that is transferred to the Mini App when it is opened. It is empty if the Mini App was launched from a keyboard button or from inline mode.
#### WebAppUser
This object contains the data of the Mini App user.
#### WebAppChat
This object represents a chat.
#### Validating data received via the Mini App
To validate data received via the Mini App, one should send the data from the Telegram.WebApp.initData field to the bot's backend. The data is a query string, which is composed of a series of field-value pairs.
You can verify the integrity of the data received by comparing the received hash parameter with the hexadecimal representation of the HMAC-SHA-256 signature of the data-check-string with the secret key, which is the HMAC-SHA-256 signature of the bot's token with the constant string WebAppData used as a key.
Data-check-string is a chain of all received fields, sorted alphabetically, in the format key=<value> with a line feed character ('\n', 0x0A) used as separator – e.g., 'auth_date=<auth_date>\nquery_id=<query_id>\nuser=<user>'.
The full check might look like:
To prevent the use of outdated data, you can additionally check the auth_date field, which contains a Unix timestamp of when it was received by the Mini App.
Once validated, the data may be used on your server. Complex data types are represented as JSON-serialized objects.
#### Events Available for Mini Apps
The Mini App can receive events from the Telegram app, onto which a handler can be attached using the Telegram.WebApp.onEvent(eventType, eventHandler) method. Inside eventHandler the this object refers to Telegram.WebApp, the set of parameters sent to the handler depends on the event type. Below is a list of possible events:
#### Adding Bots to the Attachment Menu
Attachment menu integration is currently only available for major advertisers on the Telegram Ad Platform. However, all bots can use it in the test server environment. Talk to Botfather on the test server to set up the integration.
A special link is used to add bots to the attachment menu:
https://t.me/botusername?startattachorhttps://t.me/botusername?startattach=command
> For example, open this attachment menu link for @DurgerKingBot, then use the  menu in any private chat.
Opening the link prompts the user to add the bot to their attachment menu. If the bot has already been added, the attachment menu will open in the current chat and redirect to the bot there (if the link is opened from a 1-on-1 chat). If a non-empty startattach parameter was included in the link, it will be passed to the Mini App in the start_param field and in the GET parameter tgWebAppStartParam.
The following link formats are also supported:
https://t.me/username?attach=botusernamehttps://t.me/username?attach=botusername&startattach=commandhttps://t.me/+1234567890?attach=botusernamehttps://t.me/+1234567890?attach=botusername&startattach=command
These links open the Mini App in the attachment menu in the chat with a specific user. If the bot wasn't already added to the attachment menu, the user will be prompted to do so. If a non-empty startattach parameter was included in the link, it will be passed to the Mini App in the start_param field and in the GET parameter tgWebAppStartParam.
Bot API 6.1+ supports a new link format:
https://t.me/botusername?startattach&choose=users+botshttps://t.me/botusername?startattach=command&choose=groups+channels
Opening such a link prompts the user to choose a specific chat and opens the attachment menu in that chat. If the bot wasn't already added to the attachment menu, the user will be prompted to do so. You can specify which types of chats the user will be able to choose  from. It can be one or more of the following types: users, bots, groups, channels separated by a + sign. If a non-empty startattach parameter was included in the link, it will be passed to the Mini App in the start_param field and in the GET parameter tgWebAppStartParam.
### Testing Mini Apps
#### Using bots in the test environment
To log in to the test environment, use either of the following:
- iOS: tap 10 times on the Settings icon > Accounts > Login to another account > Test.
- Telegram Desktop: open ☰ Settings > Shift + Alt + Right click ‘Add Account’ and select ‘Test Server’.
- macOS: click the Settings icon 10 times to open the Debug Menu, ⌘ + click ‘Add Account’ and log in via phone number.
The test environment is completely separate from the main environment, so you will need to create a new user account and a new bot with @BotFather.
After receiving your bot token, you can send requests to the Bot API in this format:
> Note: When working with the test environment, you may use HTTP links without TLS to test your Mini App.
#### Debug Mode for Mini Apps
Use these tools to find app-specific issues in your Mini App:
Android
- Enable USB-Debugging on your device.
- In Telegram Settings, scroll all the way down, press and hold on the version number two times.
- Choose Enable WebView Debug in the Debug Settings.
- Connect your phone to your computer and open chrome://inspect/#devices in Chrome – you will see your Mini App there when you launch it on your phone.
Telegram Desktop on Windows and Linux
- Download and launch the Beta Version of Telegram Desktop on Windows or Linux (not supported on Telegram Desktop for macOS yet).
- Go to Settings > Advanced > Experimental settings > Enable webview inspection.
- Right click in the WebView and choose Inspect.
Telegram macOS
- Download and launch the Beta Version of Telegram macOS.
- Quickly click 5 times on the Settings icon to open the debug menu and enable “Debug Mini Apps”.
- Right click in the Mini App and choose Inspect Element.
