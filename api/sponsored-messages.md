# Sponsored messages

Related TL schema:

#### Getting sponsored messages

Each time the user opens a channel, channels.getSponsoredMessages must be called to receive sponsored messages available for this channel. The result must be cached for 5 minutes.

> More about sponsored messages on Telegram

#### Displaying sponsored messages

Sponsored messages must be displayed below all other posts in the channel, after the user scrolls further down, past the last message. The promoted channel or bot specified in the from_id or chat_invite mutually exclusive fields must be displayed as the author of the message. The message should also contain a button at the bottom with one of the following labels:

- View Bot — if a bot is being promoted. Tapping the button must open the chat with the bot. If start_param is specified, the app must use the deep linking mechanism to open the bot.

- View Channel — if a channel is being promoted. Tapping the button must open the channel using the from_id or by importing the chat_invite_hash invitation link hash ».

- View Post — if a channel is being promoted and channel_post is specified. Tapping the button must open the particular channel post.

- Launch App — if the app flag is set, the specified Mini App should be opened when clicking on the button.

- Open Website — If the webpage flag is set, clicking on the button should open the external website specified in webpage.url.

- The contents of the button_text field — if the button_text field is set.

The message should be marked as "Recommended" instead of "Sponsored" if the recommended flag is set.

A profile photo bubble should be displayed for the sponsored message, like for messages sent in groups, using:

- app.photo, if the app flag is set, otherwise

- webpage.photo, if the webpage flag is set, otherwise

- The profile picture of the chat in chat_invite, if the chat_invite flag is set, otherwise

- webpage.photo, if the webpage flag is set, otherwise

- The profile picture of the peer in from_id, if the show_peer_photo flag is set.

A sender name should be displayed for the sponsored message, like for messages sent in groups, using:

- app.title, if the app flag is set, otherwise

- webpage.site_name, if the webpage flag is set, otherwise

- The title of the chat in chat_invite, if the chat_invite flag is set.

If the sponsor_info or additional_info flags are set, an additional "Sponsor info" menu item must be present in the message context menu (the menu that pops up when clicking on a button), that when clicked, displays the contents of the flags.

#### Counting sponsored message views

Once the entire text is shown on the screen (excluding the button), channels.viewSponsoredMessage must be called with the random_id of the sponsored message.

#### Clicking on sponsored messages

If the user either:

- Clicks on a link in the sponsored message

- Opens a sponsored chat or a sponsored website via the associated button

- Opens the sponsored chat via the sponsored message name, the sponsored message photo, or a mention in the sponsored message

channels.clickSponsoredMessage must be called with the random_id of the sponsored message.

#### Testing sponsored messages

For the channel https://t.me/SecretAdTestChannel the system will always return a sponsored message: promoting either a channel, a particular message in a channel, or a bot with a start parameter.

---

#### Sponsored messages in third-party apps

Telegram continues to grow worldwide, in part thanks to third-party apps using the Telegram API. To cover the increasing costs that come with this growth, Telegram added sponsored messages – a paid privacy-friendly way to promote bots and channels.

If their app allows its users to access content from Telegram channels, third-party developers using the Telegram API are required to support and properly display official sponsored messages in their apps by January 1, 2022. Unfortunately, Telegram cannot financially sustain third-party apps that do not display sponsored messages and they will have to be disconnected.

Telegram's API usage will continue to be free of charge for all developers. The rules regarding monetization in third-party apps remain the same: developers are allowed to monetize their coding efforts through advertising of their own or other legitimate means, provided that all the methods of monetization used in their apps are prominently mentioned in their app store descriptions.

