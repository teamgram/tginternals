# Connected business bots

Business users can connect Telegram bots that will process and answer messages on their behalf. This allows businesses to seamlessly integrate any existing tools and workflows, or add AI assistants that manage their chats.

```
inputBusinessBotRecipients#c4e5921e flags:# existing_chats:flags.0?true new_chats:flags.1?true contacts:flags.2?true non_contacts:flags.3?true exclude_selected:flags.5?true users:flags.4?Vector<InputUser> exclude_users:flags.6?Vector<InputUser> = InputBusinessBotRecipients;

businessBotRecipients#b88cf373 flags:# existing_chats:flags.0?true new_chats:flags.1?true contacts:flags.2?true non_contacts:flags.3?true exclude_selected:flags.5?true users:flags.4?Vector<long> exclude_users:flags.6?Vector<long> = BusinessBotRecipients;

connectedBot#cd64636c flags:# bot_id:long recipients:BusinessBotRecipients rights:BusinessBotRights = ConnectedBot;

account.connectedBots#17d7f87b connected_bots:Vector<ConnectedBot> users:Vector<User> = account.ConnectedBots;

botBusinessConnection#8f34b2f5 flags:# disabled:flags.1?true connection_id:string user_id:long dc_id:int date:int rights:flags.2?BusinessBotRights = BotBusinessConnection;

updateBotBusinessConnect#8ae5c97a connection:BotBusinessConnection qts:int = Update;
updateBotNewBusinessMessage#9ddb347c flags:# connection_id:string message:Message reply_to_message:flags.0?Message qts:int = Update;
updateBotEditBusinessMessage#7df587c flags:# connection_id:string message:Message reply_to_message:flags.0?Message qts:int = Update;
updateBotDeleteBusinessMessage#a02a982e connection_id:string peer:Peer messages:Vector<int> qts:int = Update;
updateBusinessBotCallbackQuery#1ea2fda7 flags:# query_id:long user_id:long connection_id:string message:Message reply_to_message:flags.2?Message chat_instance:long data:flags.0?bytes = Update;

---functions---

account.updateConnectedBot#66a08c7e flags:# deleted:flags.1?true rights:flags.0?BusinessBotRights bot:InputUser recipients:InputBusinessBotRecipients = Updates;
account.getConnectedBots#4ea4c80f = account.ConnectedBots;

account.toggleConnectedBotPaused#646e1097 peer:InputPeer paused:Bool = Bool;
account.disablePeerConnectedBot#5e437ed9 peer:InputPeer = Bool;

account.getBotBusinessConnection#76a86270 connection_id:string = Updates;

invokeWithBusinessConnection#dd289f8e {X:Type} connection_id:string query:!X = X;
```

Currently just one business bot may be connected to a user account.
Bots which may be connected to user accounts have the user.bot_business flag set; trying to connect a non-business bot will emit a BOT_BUSINESS_MISSING error.

Use account.updateConnectedBot » to connect a business bot to the current account, or to change the connection settings.
Use account.updateConnectedBot » with the deleted flag set to disconnect a business bot from the current account.
Use account.getConnectedBots » list all currently connected business bots.

Use account.toggleConnectedBotPaused » to pause or unpause a specific chat, temporarily disconnecting it from all business bots (equivalent to temporarily specifying it in recipients.exclude_users during initial configuration with account.updateConnectedBot »).
Use account.disablePeerConnectedBot » to permanently disconnect a specific chat from all business bots (equivalent to specifying it in recipients.exclude_users during initial configuration with account.updateConnectedBot »); to reconnect of a chat disconnected using this method the user must reconnect the entire bot by invoking account.updateConnectedBot ».

Note that invoking the above two methods will also add the peer to the recipients.exclude_users field of the related connectedBot (or to recipients.users, if the inversion recipients.exclude_selected flag is set).

The above two methods should be invoked when pressing the appropriate buttons in the action bar, see here » for more info on the business bot action bar that should be displayed on all peers currently managed by the bot, according to the action bar flags ».

Connecting or disconnecting a business bot or changing the connection settings will emit an updateBotBusinessConnect update to the bot, with the new settings and a connection_id that will be used by the bot to handle updates from and send messages as the user.

According to the specified settings, the bot will start receiving updateBotNewBusinessMessage, updateBotEditBusinessMessage, updateBotDeleteBusinessMessage updates containing messages sent to the connected user via the business connection.

Bots may invoke account.getBotBusinessConnection to re-fetch the updateBotBusinessConnect constructor associated with a specific connection_id.
This is needed for example for freshly logged in bots that are receiving some updateBotNewBusinessMessage, etc. updates because some users have already connected to the bot before it could login.
In this case, the bot is receiving messages from the business connection, but it hasn't cached the associated updateBotBusinessConnect with info about the connection (can it reply to messages? etc.) yet, and cannot receive the old ones because they were sent when the bot wasn't logged into the session yet.
This method can be used to fetch info about a not-yet-cached business connection, and should not be invoked if the info is already cached or to fetch changes, as eventual changes will automatically be sent as new updateBotBusinessConnect updates to the bot, using the usual update delivery methods ».

The bot will be able to invoke the following methods on behalf of the user via a business connection (according to the businessBotRights passed to account.updateConnectedBot), by wrapping the query in a invokeWithBusinessConnection », passing the connection ID:

- account.setGlobalPrivacySettings

- account.updateProfile

- messages.deleteMessages

- messages.editMessage

- messages.readHistory

- messages.sendMedia

- messages.sendMessage

- messages.sendMultiMedia

- messages.setTyping

- messages.updatePinnedMessage

- payments.convertStarGift

- payments.exportInvoice

- payments.getPaymentForm

- payments.getSavedStarGifts

- payments.getStarsStatus

- payments.sendStarsForm

- payments.transferStarGift

- payments.upgradeStarGift

- stories.deleteStories

Make sure to always send queries wrapped in an invokeWithBusinessConnection to the datacenter ID, specified in the dc_id field of the botBusinessConnection that is being used.

Note that a JSON version of the full list of business-ready methods is also available in the RPC db ».

messages.uploadMedia may also be used in business connections, not by wrapping it in invokeWithBusinessConnection », but rather by specifying the business connection ID in the business_connection_id parameter.

stories.sendStory and stories.editStory can also be used to post and edit stories on behalf of a connected business account: in this case, simply pass the business account's peer in peer, without wrapping the request in an invokeWithBusinessConnection » query.
Note that stories.editStory can only be used to edit stories posted by the same business bot on behalf of the user.

A BUSINESS_CONNECTION_INVALID RPC error (or for some business methods, BOT_METHOD_INVALID) will be emitted when using invokeWithBusinessConnection » if the connection_id passed to invokeWithBusinessConnection » is invalid or was changed (by a change of the business connection parameters, in this case a new updateBotBusinessConnect update will be emitted with the new connection_id).

A BUSINESS_CONNECTION_NOT_ALLOWED RPC error will be emitted when using invokeWithBusinessConnection » if either:

- The method was invoked by a user (obviously, as users cannot invoke methods over a business connection).

- The method was invoked by a bot, but business mode was disabled in @botfather.

- The method was invoked by a bot, but this method cannot be invoked over a business connection.

A BOT_ACCESS_FORBIDDEN RPC error will be emitted when using invokeWithBusinessConnection », or the other business-ready methods that do not require invokeWithBusinessConnection » if the specified query attempted an operation that is not allowed over a business connection (i.e. editing a story not uploaded by the business bot, and so on).

Messages sent by business bots on behalf of the user using this method will have the via_business_connection flag set, indicating that the message was sent by the business bot indicated in message.via_bot_id.

Messages sent by business bots on behalf of the user may also contain inline keyboards, including callback buttons, which when pressed will emit an updateBusinessBotCallbackQuery which should be handled as specified here » (without wrapping the query in an invokeWithBusinessConnection).

#### Transferring stars from a business account to the business bot

inputInvoiceBusinessBotTransferStars may be used to transfer stars from the balance of a user account connected to a business bot, to the balance of the business bot, see here » for more info on the full flow.

