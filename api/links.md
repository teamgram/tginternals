# Deep links
Telegram clients must handle special tg:// and t.me deep links encountered in messages, link entities and in other apps by registering OS handlers.
Links are generally available in two flavors: t.me HTTPS links and tg: URIs.
t.me link syntax examples:
- t.me/path?query
- http://t.me/path?query
- https://t.me/path?query
Where t.me can also be telegram.me, telegram.dog, and the domain specified in the me_url_prefix field of the global configuration, obtainable using help.getConfig.
tg: link syntax examples:
- tg:path?query
- tg://path?query
The #fragment part is always ignored when parsing Telegram deep links.
Also note that whenever a <username>.t.me link is encountered and <username>:
- Is not equal to:
- www
- Any of the values specified in this list ».
- AND is not a single letter
- AND is a valid username
...it should be treated exactly as a t.me/<username>/ link (generate a t.me/<username>/ link and append the rest of the path (if present) and the query string (if present)).
### Public username links
Used to link to public users, groups and channels, see here for more info on how to handle them ».
t.me syntax:
tg: syntax:
Parameters:
Note that message links have the same syntax, with extra parameters.
### Temporary profile links
Used to link to user profiles, generated using contacts.exportContactToken.
These links can be generated even for profiles that don't have a username, and they have an expiration date, specified by the expires field of the exportedContactToken constructor returned by contacts.exportContactToken.
t.me syntax:
tg: syntax:
Parameters:
### Phone number links
Used to link to public and private users by their phone number.
t.me syntax:
tg: syntax:
Parameters:
Note that chat invite links have the same syntax, but <phone_number> won't be a valid phone number.
### Chat invite links
Used to invite users to private groups and channels, see here for more info on how to generate such links ».
t.me syntax:
t.me syntax (legacy):
tg: syntax:
Parameters:
### Chat folder links
Used to invite users to private groups and channels, see here for more info on how to generate such links ».
t.me syntax:
tg: syntax:
Parameters:
### Message links
Used to link to specific messages in public or private groups and channels.
t.me syntax (public links):
t.me syntax (private links):
tg: syntax (public links):
tg: syntax (private links):
Parameters:
Note that since a forum topic ID is actually the ID of the service message that created the topic, whenever the client resolves a message link that points to a messageActionTopicCreate service message, it should open the topic, instead.
Also, if the message ID is 1 and the linked-to supergroup is a forum, the "General" topic should be opened instead of the first message of the supergroup.
### Forum topic links
Used to link to a specific forum topic.
The syntax is exactly the same as for message links, because the topic ID is actually the ID of the service message that created the topic, so whenever the client resolves a message link that points to a messageActionTopicCreate service message, it should open the topic, instead.
Also, if the message ID is 1 and the linked-to supergroup is a forum, the "General" topic should be opened instead of the first message of the supergroup.
### Share links
Used to share a prepared message and URL into a chosen chat's text field.
These links should be handled as follows:
- Open a dialog selection prompt
- After selection: validate, trim and enter the URL at the beginning of the text field
- Append a newline to the text field
- Append and select the text, if present
t.me syntax:
tg: syntax:
Parameters:
### Video chat/Livestream links
Used to join video/voice chats in groups, and livestreams in channels.
Such links are generated using phone.exportGroupCallInvite.
Note that voicechat links are deprecated, the API will always export videochat links for video and voice chats in groups, clients should support parsing the old link format only for backwards compatibility.
t.me syntax:
tg: syntax:
Parameters:
### Stickerset links
Used to import stickersets or custom emoji stickersets as described here ».
t.me syntax:
tg: syntax:
Parameters:
### Custom emoji stickerset links
Used to import custom emoji stickersets as described here ».
t.me syntax:
tg: syntax:
Parameters:
### Story links
Used to link to a Telegram Story », generated using the procedure specified here ».
t.me syntax:
tg: syntax:
Parameters:
### Boost links
Used by users to boost channels », granting them the ability to post stories and further perks.
Use the channel information to boost the channel as described here ».
t.me syntax (public channels):
t.me syntax (private channels):
tg: syntax (public channels):
tg: syntax (private channels):
Parameters:
### Proxy links
Used to share a proxy server that can be used to connect to Telegram.
#### MTProxy links
Used for MTProxies ».
t.me syntax:
tg: syntax:
Parameters:
#### Socks5 proxy links
Used for socks5 proxies.
t.me syntax:
tg: syntax:
Parameters:
### Theme links
Used to install themes ».
t.me syntax:
tg: syntax:
Parameters:
### Wallpaper links
Used to share and install chat backgrounds (wallpapers): see here for more info on the various wallpaper and fill types ».
#### Image wallpapers
Used for image-based wallpapers ».
t.me syntax:
tg: syntax:
Parameters:
#### Solid fill wallpapers
Used for fill wallpapers » with a solid fill ».
t.me syntax:
tg: syntax:
Parameters:
#### Gradient fill wallpapers
Used for fill wallpapers » with a gradient fill ».
t.me syntax:
tg: syntax:
Parameters:
#### Freeform gradient fill wallpapers
Used for fill wallpapers » with a freeform gradient fill ».
t.me syntax:
tg: syntax:
Parameters:
#### Solid pattern wallpapers
Used for pattern wallpapers » with a solid fill ».
t.me syntax:
tg: syntax:
Parameters:
#### Gradient pattern wallpapers
Used for pattern wallpapers » with a gradient fill ».
t.me syntax:
tg: syntax:
Parameters:
#### Freeform gradient pattern wallpapers
Used for pattern wallpapers » with a freeform gradient fill ».
t.me syntax:
tg: syntax:
Parameters:
### Bot links
Used to link to bots.
t.me syntax:
tg: syntax:
Parameters:
### Group/channel bot links
Used to add bots to groups or channels.
First of all, check that the <bot_username> indeed links to a bot.
Then, for group links:
- If the admin parameter is not provided:
- Bring up a dialog selection of groups where the user can add members
- Add the bot to the group
- If a parameter is provided, invoke messages.startBot with the appropriate parameter
- If the admin parameter is provided:
- Bring up a dialog selection of groups where the user can add/edit admins
- If the bot is already an admin of the group, combine existing admin rights with the admin rights in admin
- Add the bot as admin/modify admin permissions to the new rights
- If a parameter is provided, invoke messages.startBot with the appropriate parameter
For channel links:
- Bring up a dialog selection of channels where the user can add/edit admins
- If the bot is already an admin of the channel, combine existing admin rights with the admin rights in admin
- Add the bot as admin/modify admin permissions to the new rights
t.me syntax (groups):
tg: syntax (groups):
t.me syntax (channels):
tg: syntax (channels):
Parameters:
### Game links
Used to share games.
These links should be handled as follows:
- Check if bot_username is indeed a bot username, if so then
- Bring up a dialog selection prompt
- Send the game to the selected dialog using an inputMediaGame with an inputGameShortName as specified in the game docs.
t.me syntax:
tg: syntax:
Parameters:
### Settings links
#### Settings link
Used to bring the user to the app settings.
tg: syntax:
No parameters.
#### Change phone number link
Used to bring the user to the phone number modification page, invoking account.sendChangePhoneCode and account.changePhone.
tg: syntax:
No parameters.
#### Active sessions link
Used to bring the user to the active sessions page, calling account.getAuthorizations.
tg: syntax:
No parameters.
#### Folder settings link
Used to bring the user to the folder settings.
tg: syntax:
No parameters.
#### Language settings link
Used to bring the user to the language settings.
tg: syntax:
No parameters.
#### Privacy and security settings link
Used to bring the user to the privacy and security settings.
tg: syntax:
No parameters.
#### Autodelete settings link
Used to bring the user to the message autodeletion settings.
tg: syntax:
No parameters.
#### Profile settings link
Used to bring the user to the profile settings menu.
tg: syntax:
No parameters.
#### Theme settings link
Used to bring the user to the theme settings section of the app.
tg: syntax:
No parameters.
### Login code link
Contains the phone number verification code to use during user authorization ».
t.me syntax:
tg: syntax:
Parameters:
### Invoice links
Used to initiate payment of an invoice », generated using payments.exportedInvoice.
t.me syntax:
tg: syntax:
Parameters:
### Language pack links
Used to import custom language packs using langpack.getLangPack.
t.me syntax:
tg: syntax:
Parameters:
### Telegram Passport links
See the Telegram Passport documentation for parameters and usage ».
tg: syntax:
### Phone confirmation links
Different from login code links.
These links are used to confirm ownership of the phone number, to prevent account deletion: see the account deletion docs for more info on how to handle them ».
t.me syntax:
tg: syntax:
Parameters:
### Premium multigift links
Used to bring the user to the screen used for gifting Telegram Premium subscriptions to friends, see here for more info on gifting Telegram Premium to multiple users ».
This link is used to invite users to gift Premium subscription to other users, see here » for the different link type containing the actual giftcodes that can be used to import a gifted Telegram Premium subscription.
tg: syntax:
Parameters:
### Premium referrer links
Used by official apps to show the Telegram Premium subscription page.
tg: syntax:
Parameters:
### Premium giftcode links
Used to process Telegram Premium giftcode links.
tg: syntax:
t.me syntax:
Parameters:
### QR code login links
Used by the QR code login flow ».
tg: syntax:
Parameters:
### Mini App links
Used to install and open a bot attachment or side menu ».
Clients should first install the associated bot attachment or side menu entry as specified here », and if the user accepts the installation prompt, open the Mini App using the following logic.
After installing the attachment/side menu entry globally, opens the associated mini app using messages.requestSimpleWebView with the from_side_menu flag set, regardless of the currently open Telegram chat (in fact, the Mini App should opened with that flag even if the client itself is minimized).
t.me syntax:
Note that Direct Mini App links have a similar syntax, with an additional short_name parameter to identify a specific Mini App owned by the bot.
tg: syntax:
Parameters:
### Direct mini app links
Used to share Direct link Mini apps.
These links are different from bot attachment menu deep links, because they don't require the user to install an attachment menu, and a single bot can offer multiple named mini apps, distinguished by their short_name.
These links should be handled as specified in the direct link Mini Apps documentation ».
t.me syntax:
tg: syntax:
Note that Mini App links have a similar syntax, without a short_name parameter.
Parameters:
### Bot attachment or side menu links
Used to install and open a bot attachment or side menu » in a certain chat.
For all link types, clients should first install the associated bot attachment or side menu entry as specified here », and if the user accepts the installation prompt, open the Mini App using the following logic, depending on the link subtype:
#### Open in current chat
After installing the attachment/side menu entry globally, opens the associated mini app using messages.requestWebView in the currently open chat, by passing it to the peer parameter of messages.requestWebView.
If the current chat is not supported by the attachMenuBot.peer_types field:
- If the user has just installed the attachment menu in the previous step, notify the user that the attachment menu was installed successfully.
- Otherwise, notify the user that the attachment menu webapp can't be opened in the specified chat.
t.me syntax:
tg: syntax:
Parameters:
#### Open in specific chat
After installing the attachment/side menu entry globally, opens the associated mini app using messages.requestWebView in a specific chat (passed to the peer parameter of messages.requestWebView).
t.me syntax:
tg: syntax:
If the specified chat is not supported by the attachMenuBot.peer_types field:
- If the user has just installed the attachment menu in the previous step, notify the user that the attachment menu was installed successfully.
- Otherwise, notify the user that the attachment menu webapp can't be opened in the specified chat.
Parameters:
#### Open in any chat
After installing the attachment/side menu entry globally, opens a dialog selection form that will open the attachment menu mini app using messages.requestWebView in a specific chat (passed it to the peer parameter of messages.requestWebView).
t.me syntax:
tg: syntax:
Parameters:
### ID links
ID links are merely an abstraction offered by the bot API to simplify construction of inputMessageEntityMentionName and inputKeyboardButtonUserProfile constructors, and should be ignored by normal clients.
tg: syntax:
Parameters:
### Emoji links
Emoji links are merely an abstraction offered by the bot API to simplify construction of messageEntityCustomEmoji constructors, and should be ignored by normal clients.
tg: syntax:
Parameters:
### Unsupported links
If a client encounters a tg: link type not listed on this page, help.getDeepLinkInfo should be invoked with just the path component of the link.
Schema:
The method may return formatted text, containing for example:
- A description of what the link does or,
- An explanation of why a certain link isn't supported by the app;
And/or an invitation to upgrade to the latest version of the client app to be able to use the link: in this case, the result update_app flag will also be set, and the app should directly link to a store or attempt updating to the latest version.
Example links that can be used for testing:
- tg://need_update_for_some_feature?test=a
- tg:some_unsupported_feature?test=b
In these cases, help.getDeepLinkInfo should be invoked with the following parameters:
- help.getDeepLinkInfo({path: "need_update_for_some_feature"})
- help.getDeepLinkInfo({path: "some_unsupported_feature"})
Note that this method should not be called for unrecognized t.me links, the usual HTTP link handling logic should be used, instead.
