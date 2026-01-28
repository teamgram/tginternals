# Buttons

Users can interact with your bot via buttons or even inline buttons, straight from inline messages in any chat.
This article describes the full button flow, using the MTProto API.

For a simplified description using the HTTP bot API, see here ».

### Buttons

```
keyboardButton#a2fa4880 text:string = KeyboardButton;
keyboardButtonUrl#258aff05 text:string url:string = KeyboardButton;
keyboardButtonCallback#35bbdb6b flags:# requires_password:flags.0?true text:string data:bytes = KeyboardButton;
keyboardButtonRequestPhone#b16a6c29 text:string = KeyboardButton;
keyboardButtonRequestGeoLocation#fc796b3f text:string = KeyboardButton;
keyboardButtonSwitchInline#93b9fbb5 flags:# same_peer:flags.0?true text:string query:string peer_types:flags.1?Vector<InlineQueryPeerType> = KeyboardButton;
keyboardButtonGame#50f41ccf text:string = KeyboardButton;
keyboardButtonBuy#afd93fbb text:string = KeyboardButton;
keyboardButtonUrlAuth#10b78d29 flags:# text:string fwd_text:flags.0?string url:string button_id:int = KeyboardButton;
inputKeyboardButtonUrlAuth#d02e7fd4 flags:# request_write_access:flags.0?true text:string fwd_text:flags.1?string url:string bot:InputUser = KeyboardButton;
keyboardButtonRequestPoll#bbc7515d flags:# quiz:flags.0?Bool text:string = KeyboardButton;
inputKeyboardButtonRequestPeer#c9662d05 flags:# name_requested:flags.0?true username_requested:flags.1?true photo_requested:flags.2?true text:string button_id:int peer_type:RequestPeerType max_quantity:int = KeyboardButton;

keyboardButtonRow#77608b83 buttons:Vector<KeyboardButton> = KeyboardButtonRow;

replyKeyboardHide#a03e5b85 flags:# selective:flags.2?true = ReplyMarkup;
replyKeyboardForceReply#86b40b08 flags:# single_use:flags.1?true selective:flags.2?true placeholder:flags.3?string = ReplyMarkup;
replyKeyboardMarkup#85dd99d1 flags:# resize:flags.0?true single_use:flags.1?true selective:flags.2?true persistent:flags.4?true rows:Vector<KeyboardButtonRow> placeholder:flags.3?string = ReplyMarkup;
replyInlineMarkup#48a30254 rows:Vector<KeyboardButtonRow> = ReplyMarkup;

message#9815cec8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true from_scheduled:flags.18?true legacy:flags.19?true edit_hide:flags.21?true pinned:flags.24?true noforwards:flags.26?true invert_media:flags.27?true flags2:# offline:flags2.1?true video_processing_pending:flags2.4?true paid_suggested_post_stars:flags2.8?true paid_suggested_post_ton:flags2.9?true id:int from_id:flags.8?Peer from_boosts_applied:flags.29?int peer_id:Peer saved_peer_id:flags.28?Peer fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long via_business_bot_id:flags2.0?long reply_to:flags.3?MessageReplyHeader date:int message:string media:flags.9?MessageMedia reply_markup:flags.6?ReplyMarkup entities:flags.7?Vector<MessageEntity> views:flags.10?int forwards:flags.10?int replies:flags.23?MessageReplies edit_date:flags.15?int post_author:flags.16?string grouped_id:flags.17?long reactions:flags.20?MessageReactions restriction_reason:flags.22?Vector<RestrictionReason> ttl_period:flags.25?int quick_reply_shortcut_id:flags.30?int effect:flags2.2?long factcheck:flags2.3?FactCheck report_delivery_until_date:flags2.5?int paid_message_stars:flags2.6?long suggested_post:flags2.7?SuggestedPost = Message;

---functions---

messages.sendMessage#fe05dc9a flags:# no_webpage:flags.1?true silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
```

Bots can attach a ReplyMarkup constructor to outgoing messages, to attach an inline keyboard or a custom reply keyboard:

- replyKeyboardMarkup - Sends a custom reply keyboard.     User clients receiving such a constructor should display a special keyboard with custom reply options.

- replyKeyboardHide - Hides the custom reply keyboard.     User clients receiving this constructor should hide the custom reply keyboard opened by replyKeyboardMarkup

- replyKeyboardForceReply - Sends a force reply constructor     User clients receiving a message with this constructor should act as if the user had clicked on the reply button of the message, displaying the reply UI.

- replyInlineMarkup - Attaches an inline keyboard to the message, allowing users to send callback data to the bot without sending actual messages to the current chat.

### Pressing buttons

```
requestPeerTypeUser#5f3b8a00 flags:# bot:flags.0?Bool premium:flags.1?Bool = RequestPeerType;
requestPeerTypeChat#c9f06e1b flags:# creator:flags.0?true bot_participant:flags.5?true has_username:flags.3?Bool forum:flags.4?Bool user_admin_rights:flags.1?ChatAdminRights bot_admin_rights:flags.2?ChatAdminRights = RequestPeerType;
requestPeerTypeBroadcast#339bef6c flags:# creator:flags.0?true has_username:flags.3?Bool user_admin_rights:flags.1?ChatAdminRights bot_admin_rights:flags.2?ChatAdminRights = RequestPeerType;

keyboardButtonRequestPeer#53d7bfd8 text:string button_id:int peer_type:RequestPeerType max_quantity:int = KeyboardButton;

messageActionRequestedPeer#31518e9b button_id:int peers:Vector<Peer> = MessageAction;

keyboardButton#a2fa4880 text:string = KeyboardButton;
keyboardButtonUrl#258aff05 text:string url:string = KeyboardButton;
keyboardButtonCallback#35bbdb6b flags:# requires_password:flags.0?true text:string data:bytes = KeyboardButton;
keyboardButtonRequestPhone#b16a6c29 text:string = KeyboardButton;
keyboardButtonRequestGeoLocation#fc796b3f text:string = KeyboardButton;
keyboardButtonRequestPoll#bbc7515d flags:# quiz:flags.0?Bool text:string = KeyboardButton;
keyboardButtonSwitchInline#93b9fbb5 flags:# same_peer:flags.0?true text:string query:string peer_types:flags.1?Vector<InlineQueryPeerType> = KeyboardButton;
keyboardButtonGame#50f41ccf text:string = KeyboardButton;
keyboardButtonBuy#afd93fbb text:string = KeyboardButton;
keyboardButtonUrlAuth#10b78d29 flags:# text:string fwd_text:flags.0?string url:string button_id:int = KeyboardButton;

// Used by bots to send a keyboardButtonUrlAuth
inputKeyboardButtonUrlAuth#d02e7fd4 flags:# request_write_access:flags.0?true text:string fwd_text:flags.1?string url:string bot:InputUser = KeyboardButton;

keyboardButtonRow#77608b83 buttons:Vector<KeyboardButton> = KeyboardButtonRow;

---functions---

messages.sendBotRequestedPeer#91b2d060 peer:InputPeer msg_id:int button_id:int requested_peers:Vector<InputPeer> = Updates;
```

Both reply and inline keyboards are composed of a vector of rows, each row containing a vector of buttons, for each column.
Each row can have a different number of columns, and user clients should properly handle clicking buttons of every type.

Buttons available only in reply keyboards:

- keyboardButton - Send a message to the chat, replying to the message that attached the reply keyboard

- keyboardButtonRequestPhone - Only in private chats, send the current user's contact to the chat, replying to the message that attached the reply keyboard

- keyboardButtonRequestGeoLocation - Only in private chats, send the current user's geolocation to the chat, replying to the message that attached the reply keyboard

- keyboardButtonRequestPoll - Only in private chats, prompts the user to create and send a poll (or a quiz poll, depending on the quiz flag), replying to the message that attached the reply keyboard

- keyboardButtonRequestPeer - Prompts the user to select and share a maximum of max_quantity peers with the bot using messages.sendBotRequestedPeer, according to the criteria specified in the RequestPeerType constructor. keyboardButtonRequestPeer.button_id must be passed to the method: the peer and the specified button_id will be received by the bot as a messageActionRequestedPeer service message.

Buttons available only in inline keyboards:

- keyboardButtonUrl - Open the URL, showing a "Do you want to open this URL?" prompt (unless the URL is one of the internal URIs, in which case the URL should be opened right away)

- keyboardButtonCallback - Send the callback data to the bot, optionally providing the user's 2FA SRP payload for identity verification, see here for more info »

- keyboardButtonSwitchInline

- If keyboardButtonSwitchInline.same_peer is set, insert the bot's username and keyboardButtonSwitchInline.query in the current chat's input field, triggering an inline query.

- If keyboardButtonSwitchInline.same_peer is not set, prompt the user to select one of their chats, and then insert the bot's username and keyboardButtonSwitchInline.query in the current chat's input field, triggering an inline query.

- keyboardButtonGame - Open the game from the attached messageMediaGame constructor, for more info see here »

- keyboardButtonBuy - Proceed to initiating the payment flow, for more info see here »

- keyboardButtonUrlAuth - Log into a website using the user's Telegram account, as specified here »

### Callback queries

keyboardButtonCallback buttons can be used to send the specified data payload back to the bot, when they are clicked.
Additionally, a bot can verify a user's identity by requiring they verify their 2FA password with SRP.

#### Sending a callback query

```
keyboardButtonGame#50f41ccf text:string = KeyboardButton;
keyboardButtonCallback#35bbdb6b flags:# requires_password:flags.0?true text:string data:bytes = KeyboardButton;

messages.botCallbackAnswer#36585ea4 flags:# alert:flags.1?true has_url:flags.3?true native_ui:flags.4?true message:flags.0?string url:flags.2?string cache_time:int = messages.BotCallbackAnswer;

---functions---

messages.getBotCallbackAnswer#9342ca07 flags:# game:flags.1?true peer:InputPeer msg_id:int data:flags.0?bytes password:flags.2?InputCheckPasswordSRP = messages.BotCallbackAnswer;
```

When the user clicks on a keyboardButtonCallback in a message sent by a bot, or generated by an inline query, messages.getBotCallbackAnswer should be called, passing the peer and ID of the message.
The same should happen when clicking on keyboardButtonGame buttons, with the difference that the game flag must be set instead of the data parameter.

Make sure to properly handle bot timeouts in the form of BOT_RESPONSE_TIMEOUT RPC errors, as the bot may be offline and unable to reply.

The returned messages.botCallbackAnswer constructor contains:

- message if specified, a message that should be shown in a non-blocking toast notification

- alert indicates whether the message should be shown as a dismissible prompt, instead of a simple toast notification

- has_url Whether an URL is present

- url if specified, the client should open the URL, without showing a confirmation prompt.     This is safe and allowed, because here bots can only return:

- Deep links to themselves »

- Deep links to a valid game they own », if the bot has manually configured games, and the clicked button was a keyboardButtonGame.

- native_ui whether to open game URLs in a WebView or in native UI.

- cache_time specifies for how long should this answer be cached, client-side

##### SRP verification

If the requires_password flag is set, the SRP 2FA payload must also be generated and attached to the query, to verify the identity of the user.

Note that the bot will NOT be able to access your password or the SRP payload.

The SRP payload will be processed exclusively on the Telegram's servers, simply returning an RPC error without passing the query to the bot if the verification fails.
This is just a way of verifying the identity of the user, mainly used by the official @botfather bot to allow securely transferring the ownership of a bot to another user.

#### Answering a callback query

```
updateBotCallbackQuery#b9cfc48d flags:# query_id:long user_id:long peer:Peer msg_id:int chat_instance:long data:flags.0?bytes game_short_name:flags.1?string = Update;

updateInlineBotCallbackQuery#691e9052 flags:# query_id:long user_id:long msg_id:InputBotInlineMessageID chat_instance:long data:flags.0?bytes game_short_name:flags.1?string = Update;

updateBusinessBotCallbackQuery#1ea2fda7 flags:# query_id:long user_id:long connection_id:string message:Message reply_to_message:flags.2?Message chat_instance:long data:flags.0?bytes = Update;

---functions---

messages.setBotCallbackAnswer#d58f130a flags:# alert:flags.1?true query_id:long message:flags.0?string url:flags.2?string cache_time:int = Bool;
```

After the user invokes messages.getBotCallbackAnswer, an updateBotCallbackQuery, updateInlineBotCallbackQuery or updateBusinessBotCallbackQuery is generated and sent to the bot, depending on whether the query originated from a normal message sent by the bot, from a message sent from an inline query, or from a message sent via a business connection.

Either way, bots must reply to the query as quickly as possible using messages.setBotCallbackAnswer:

- query_id is the query_id from messages.getBotCallbackAnswer, an updateBotCallbackQuery, updateInlineBotCallbackQuery or updateBusinessBotCallbackQuery

- message, alert, url can contain messages and URLs to trigger different client behaviour, as specified above »

- cache_time indicates the maximum amount of time in seconds that the result of the callback query may be cached by the client.

If a game_short_name is present in the update, the bot should return the URL of the game with the specified name.
The messages.setBotCallbackAnswer method must be called anyway, even if no message or url is returned, to avoid timeouts on the client.

