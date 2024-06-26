# Buttons

Users can interact with your bot via buttons or even inline buttons, straight from inline messages in any chat.
This article describes the full button flow, using the MTProto API.

For a simplified description using the HTTP bot API, see here ».

### Buttons

Bots can attach a ReplyMarkup constructor to outgoing messages, to attach an inline keyboard or a custom reply keyboard:

- replyKeyboardMarkup - Sends a custom reply keyboard.     User clients receiving such a constructor should display a special keyboard with custom reply options.

- replyKeyboardHide - Hides the custom reply keyboard.     User clients receiving this constructor should hide the custom reply keyboard opened by replyKeyboardMarkup

- replyKeyboardForceReply - Sends a force reply constructor     User clients receiving a message with this constructor should act as if the user had clicked on the reply button of the message, displaying the reply UI.

- replyInlineMarkup - Attaches an inline keyboard to the message, allowing users to send callback data to the bot without sending actual messages to the current chat.

### Pressing buttons

Both reply and inline keyboards are composed of a vector of rows, each row containing a vector of buttons, for each column.
Each row can have a different number of columns, and user clients should properly handle clicking buttons of every type.

Buttons available only in reply keyboards:

- keyboardButton - Send a message to the chat, replying to the message that attached the reply keyboard

- keyboardButtonRequestPhone - Only in private chats, send the current user's contact to the chat, replying to the message that attached the reply keyboard

- keyboardButtonRequestGeoLocation - Only in private chats, send the current user's geolocation to the chat, replying to the message that attached the reply keyboard

- keyboardButtonRequestPoll - Only in private chats, prompts the user to create and send a poll (or a quiz poll, depending on the quiz flag), replying to the message that attached the reply keyboard

- keyboardButtonRequestPeer - Prompts the user to select and share a peer with the bot using messages.sendBotRequestedPeer, according to the criteria specified in the RequestPeerType constructor. keyboardButtonRequestPeer.button_id must be passed to the method: the peer and the specified button_id will be received by the bot as a messageActionRequestedPeer service message.

Buttons available only in inline keyboards:

- keyboardButtonUrl - Open the URL, showing a "Do you want to open this URL?" prompt (unless the URL is one of the internal URIs, in which case the URL should be opened right away)

- keyboardButtonCallback - Send the callback data to the bot, optionally providing the user's 2FA SRP payload for identity verification, see here for more info »

- keyboardButtonSwitchInline

- If keyboardButtonSwitchInline.same_peer is set, insert the bot's username and keyboardButtonSwitchInline.query in the current chat's input field, triggering an inline query.

- If keyboardButtonSwitchInline.same_peer is not set, prompt the user to select one of their chats, and then insert the bot's username and keyboardButtonSwitchInline.query in the current chat's input field, triggering an inline query.

- keyboardButtonGame - Open the game from the attached messageMediaGame constructor, for more info see here »

- keyboardButtonBuy - Proceed to initiating the payment flow, for more info see here »

- keyboardButtonUrlAuth - Log into a website using the user's Telegram account, as specified here »

### Callback queries

keyboardButtonCallback buttons can be used to send the specified data payload back to the bot, when they are clicked.
Additionally, a bot can verify a user's identity by requiring they verify their 2FA password with SRP.

#### Sending a callback query

When the user clicks on a keyboardButtonCallback in a message sent by a bot, or generated by an inline query, messages.getBotCallbackAnswer should be called, passing the peer and ID of the message.
The same should happen when clicking on keyboardButtonGame buttons, with the difference that the game flag must be set instead of the data parameter.

Make sure to properly handle bot timeouts in the form of BOT_RESPONSE_TIMEOUT RPC errors, as the bot may be offline and unable to reply.

The returned messages.botCallbackAnswer constructor contains:

- message if specified, a message that should be shown in a non-blocking toast notification

- alert indicates whether the message should be shown as a dismissible prompt, instead of a simple toast notification

- has_url Whether an URL is present

- url if specified, the client should open the URL, without showing a confirmation prompt.     This is safe and allowed, because here bots can only return:

- Deep links to themselves »

- Deep links to a valid game they own », if the bot has manually configured games, and the clicked button was a keyboardButtonGame.

- native_ui whether to open game URLs in a WebView or in native UI.

- cache_time specifies for how long should this answer be cached, client-side

##### SRP verification

If the requires_password flag is set, the SRP 2FA payload must also be generated and attached to the query, to verify the identity of the user.

Note that the bot will NOT be able to access your password or the SRP payload.

The SRP payload will be processed exclusively on the Telegram's servers, simply returning an RPC error without passing the query to the bot if the verification fails.
This is just a way of verifying the identity of the user, mainly used by the official @botfather bot to allow securely transferring the ownership of a bot to another user.

#### Answering a callback query

After the user invokes messages.getBotCallbackAnswer, an updateBotCallbackQuery or updateInlineBotCallbackQuery is generated and sent to the bot, depending on whether the query originated from a normal message sent by the bot, or from a message sent from an inline query.

Either way, bots must reply to the query as quickly as possible using messages.setBotCallbackAnswer:

- query_id is the query_id from messages.getBotCallbackAnswer, an updateBotCallbackQuery or updateInlineBotCallbackQuery

- message, alert, url can contain messages and URLs to trigger different client behaviour, as specified above »

- cache_time indicates the maximum amount of time in seconds that the result of the callback query may be cached by the client.

If a game_short_name is present in the update, the bot should return the URL of the game with the specified name.
The messages.setBotCallbackAnswer method must be called anyway, even if no message or url is returned, to avoid timeouts on the client.

