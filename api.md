# Telegram APIs

We offer two kinds of APIs for developers. The Bot API allows you to easily create programs that use Telegram messages for an interface. The Telegram API and TDLib allow you to build your own customized Telegram clients. You are welcome to use both APIs free of charge.

You can also add Telegram Widgets to your website.

Designers are welcome to create Animated Stickers or Custom Themes for Telegram.

---

### Bot API

This API allows you to connect bots to our system. Telegram Bots are special accounts that do not require an additional phone number to set up. These accounts serve as an interface for code running somewhere on your server.

To use this, you don't need to know anything about how our MTProto encryption protocol works — our intermediary server will handle all encryption and communication with the Telegram API for you. You communicate with this server via a simple HTTPS-interface that offers a simplified version of the Telegram API.

> Learn more about the Bot API here »

Bot developers can also make use of our Payments API to accept payments from Telegram users around the world.

---

### TDLib – build your own Telegram

Even if you're looking for maximum customization, you don't have to create your app from scratch. Try our Telegram Database Library (or simply TDLib), a tool for third-party developers that makes it easy to build fast, secure and feature-rich Telegram apps.

TDLib takes care of all network implementation details, encryption and local data storage, so that you can dedicate more time to design, responsive interfaces and beautiful animations.

TDLib supports all Telegram features and makes developing Telegram apps a breeze on any platform. It can be used on Android, iOS, Windows, macOS, Linux and virtually any other system. The library is open source and compatible with virtually any programming language.

> Learn more about TDLib here »

---

### Telegram API

This API allows you to build your own customized Telegram clients. It is 100% open for all developers who wish to create Telegram applications on our platform. Feel free to study the open source code of existing Telegram applications for examples of how things work here. Don't forget to register your application in our system.

- Getting Started

- Security

- Optimization

- API methods

### Getting started

#### Creating an application

How to get your application identifier and create a new Telegram app.

#### User authorization

How to register a user's phone to start using the API.

#### Two-factor authentication

How to login to a user's account if they have enabled 2FA, how to change password.

#### QR code login

QR code login flow

#### Error handling

How to handle API return errors correctly.

#### Handling different data centers

How to connect to the closest DC access point for faster interaction with the API, and things to watch out for when developing a client.

#### Handling updates

How to subscribe to updates and handle them properly.

#### Handling PUSH-notifications

How to subscribe and handle them properly.

#### Channels, supergroups, gigagroups and basic groups

How to handle channels, supergroups, gigagroups, basic groups, and what's the difference between them.

#### Forums

Telegram allows creating forums with multiple distinct topics.

#### Channel statistics

Telegram offers detailed channel statistics for channels and supergroups.

#### Calling methods

Additional options for calling methods.

#### Uploading and Downloading Files

How to transfer large data batches correctly.

#### Pagination

How to fetch results from large lists of objects.

#### Client configuration

The MTProto API has multiple client configuration parameters that can be fetched with the appropriate methods.

### Security

#### Secret chats, end-to-end encryption

End-to-end-encrypted messaging.

#### Security guidelines

Important checks required in your client application.

#### Perfect Forward Secrecy

Binding temporary authorization key to permanent ones.

#### End-to-End Encryption in Voice and Video Calls

End-to-end-encrypted calls.

### Optimization

#### Client optimization

Ways to boost API interactions.

### API methods

#### Available method list

A list of available high-level methods.

#### API TL-schema, as JSON

Text and JSON-presentation of types and methods used in API.

#### Available layer list

A list of available schema versions.

### Other articles

#### Working with bots, using the MTProto API

How to work with bots using the MTProto API.

#### Commands

Bots offer a set of commands that can be used by users in private, or in a chat.

#### Buttons

Users can interact with your bot via buttons or even inline buttons, straight from inline messages in any chat.

#### Menu button

Bots can choose the behavior of the menu button shown next to the text input field.

#### Inline queries

Users can interact with your bot via inline queries, straight from the text input field in any chat.

#### Games

Bots can offer users HTML5 games to play solo or to compete against each other in groups and one-on-one chats; how to work with games in the MTProto API.

#### Mini apps

Bots can offer users interactive HTML5 mini apps to completely replace any website.

#### Attachment menu

Bots can install attachment menu entries, offering conveniently accessible, versatile mini apps.

#### Stories

Telegram users and channels can easily post and view stories through the API.

#### Similar channels

The API offers a method to obtain a list of similarly themed public channels, selected based on similarities in their subscriber bases.

#### Accent colors

Telegram users and channels can change the accent color and background pattern of their profile page and their messages!

#### Privacy settings

Telegram allows users to specify granular privacy settings, choosing which users can or can't interact with them in certain ways.

#### Search & filters

Telegram allows applying detailed message filters while looking for messages in chats.
This allows the server to filter messages based on a text query, and even on their type, and this feature is often used by graphical clients to implement features like the chat gallery, chat profile pictures and more.

#### Polls

Telegram allows sending polls and quizzes, that can be voted on by thousands, if not millions of users in chats and channels.

#### Reactions

Telegram allows users to react on any message using specific emojis, triggering cute lottie animations.

#### Emoji status

Telegram allows users to set an emoticon or a custom emoji as status, to show next to their name in chats and profiles.

#### Invite links and join requests

Channels, basic groups and supergroups may have a public username or a private invite link: private invite links may be further enhanced with per-user join requests.

#### Admin, banned and default rights for channels, supergroups and groups

How to handle admin permissions, granular bans and global permissions in channels, groups and supergroups.

#### Discussion groups

Groups can be associated to a channel as a discussion group, to allow users to discuss about posts.

#### Channel comments and message threads

Telegram allows commenting on a channel post or on a generic group message, thanks to message threads.

#### Admin log

Both supergroups and channels offer a so-called admin log, a log of recent relevant supergroup and channel actions, like the modification of group/channel settings or information on behalf of an admin, user kicks and bans, and more.

#### Pinned messages

Telegram allows pinning multiple messages on top of a specific chat.

#### Mentions

Telegram allows mentioning other users in case of urgent duckling matters, and quickly navigating to those mentions in order to read them as swiftly as possible.

#### Scheduled messages

Telegram allows scheduling messages.

#### Live geolocations

Telegram allows sending the live geolocation of a user in a chat, optionally setting a proximity alert.

#### Min constructors

Sometimes, user and channel constructors met in group chat updates may not contain full info about the user: how to handle such constructors.

#### Account deletion

How to delete a Telegram account.

#### Imported messages

Telegram allows importing messages and media from foreign chat apps.

#### Telegram Passport

How to work with Telegram Passport directly using the MTProto API.

#### Telegram Payments

How to work with Telegram Payments directly using the MTProto API.

#### Styled text with message entities

How to create styled text with message entities

#### Working with stickers

Telegram clients support displaying animated, static and video stickers.

#### Working with custom emojis

Telegram allows including custom animated, static and video emojis directly inside of messages.

#### Working with animated emojis

Graphical telegram clients should transform emojis into their respective animated version.

#### Working with animated dice

Telegram supports sending animated dice emojis.

#### Message drafts

How to handle message drafts

#### Folders

Working with folders

#### Top peer rating

If enabled, the rating of top peers indicates the relevance of a frequently used peer in a certain category (frequently messaged users, frequently used bots, inline bots, frequently visited channels and so on).

#### Handling file references

How to handle file references.

#### Seamless Telegram Login

Handle Seamless Telegram Login URL authorization requests.

#### Wallpapers

How to work with chat backgrounds.

#### Notification sounds

How to work with chat notification sounds.

#### Message transcription

How to transcribe voice messages.

#### Message translation

Telegram allows translating chat messages, and Telegram Premium users may even enable real-time chat translation.

#### Native antispam system

Admins of supergroups with a certain number of members can choose to unleash the full proactive power of Telegram's own antispam algorithms – turning on the new Aggressive mode for the automated spam filters.

#### Collectible usernames

Telegram users can make it easy for others to contact them or find their public groups and channels via usernames: clients can also assign multiple collectible usernames to accounts, supergroups and channels they own.

#### Channel boosts

Telegram Premium users can grant their favorite channels additional features like the ability to post stories by giving them boosts.

#### Giveaways & gifts

Telegram channel administrators may launch giveaways to randomly distribute Telegram Premium subscriptions and other gifts among their followers, in exchange for boosts.

#### Action bar

Sometimes, when interacting with Telegram users via private or secret chats, an action bar must be shown on top of the chat, offering convenient action buttons or notices regarding the user.

#### Saved messages

The Saved Messages chat allows users to bookmark messages and media: it's a personal cloud storage for any messages or media you may want to send or forward there.

### Contacts

Working with contacts in the API.

### Blocklist

Working with the blocklist.

### Nearby users&chats

How to work with geolocation-based features like geochats and the nearby users feature.

#### Web events

When interacting with HTML5 games and the websites of payment gateways, Telegram apps should expose the following JS APIs.

#### Takeout

Telegram's API allows users to export all of their information through the takeout API.

