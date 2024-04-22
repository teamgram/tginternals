# Inline

Users can interact with your bot via inline queries, straight from the text input field in any chat.
This article describes the full inline bot flow, using the MTProto API.

For a simplified description using the HTTP bot API, see here ».

### 1. Making an inline query

When, in a graphical client, the user starts a message with an @, clients should:

- Use the cached top peer rating for inline bots to show a list of frequently used inline bots.

- If the user chooses a bot from the recent bot list or:

- Finishes typing a full username followed by a whitespace, and if the username resolves to a valid bot

- messages.getInlineBotResults is called, with the following parameters:

- bot - The bot peer

- peer - The chat where the user made the query

- geo_point - The user's current geolocation, if the bot requires location-based inline results (the bot_inline_geo flag of the bot's user constructor will be set)

- query - What the user typed after the bot's username

- offset - If the user scrolls past the first len(results) results, and next_offset field is set, the inline query should be repeated with this offset.

### 2. Answering to an inline query

Bots can answer to incoming updateBotInlineQuery updates using messages.setInlineBotResults.
Just like its bot API counterpart, the method can be used to send a set of inline results to the user; see the constructor page for more info on the MTProto method parameters ».

In general, the method accepts a vector of InputBotInlineResult constructors, that when chosen, generates a message with optionally attached media, and even inline buttons.

### 3. Sending the inline query result

The user client should display the messages.botResults.results obtained during querying in a list, making sure to handle eventual bot timeouts in the form of a BOT_RESPONSE_TIMEOUT RPC error, by simply not displaying anything.

If either the messages.botResults.switch_pm or messages.botResults.switch_webview flags are populated, a button should be displayed on top of the result list, that when clicked, instead of sending an inline result to the chat, switches the user to a private chat with the bot (switch_pm) or to a inline mode mini app (switch_webview).

If the user instead chooses a specific BotInlineResult from the normal results list, the messages.sendInlineBotResult method should be invoked, passing:

- The query_id from messages.botResults

- The id of the chosen result

- The peer where to send the chosen result

The resulting message will have the via_bot_id field set, to indicate that the result was generated by the bot that generated the inline result.
Graphical clients should display the bot @username in the header of the message, allowing the user to click on it, automatically starting an inline query by inserting @username in the text bar.

### 4. Inline feedback

If feedback collection is enabled, the bot may receive an updateBotInlineSend when the user chooses and sends an inline result.

Even if the probability setting is set to 100%, not all inline results may be reported due to caching (see the cache_time parameter in Answering a callback query).
Feedback collection can also create load issues for popular bots, so adjust the probability setting to a lower value in such cases.

Either way, feedback collection should only be used for statistical purposes rather than functional.

The updateBotInlineSend will contain:

- id - The ID of the chosen result

- msg_id - The ID of the sent inline message

- user_id - The ID of the user that chose the result

- query - The query string that was used to obtain the result

- geo - For bots requiring location-based inline results, the user's location

### 5. Editing sent inline messages

Sent inline messages can be edited by the bot, for example in response to a button press callback query.

Simply pass the inputBotInlineMessageID specified in the updateInlineBotCallbackQuery to messages.editInlineBotMessage along with the new message, making sure to send the query to the datacenter specified in inputBotInlineMessageID.dc_id.
