# Inline Bots
Beyond sending commands in private messages or groups, users can interact with your bot via inline queries. If inline queries are enabled, users can call your bot by typing its username and a query in the text input field in any chat. The query is sent to your bot in an update. This way, people can request content from your bot in any of their chats, groups, or channels without sending any messages at all.
To enable this option, send the /setinline command to @BotFather and provide the placeholder text that the user will see in the input field after typing your bot’s name.
> See the Bot API Manual for the relevant methods and objects.
### Inline results
Inline bots support all types of content available in Telegram (20 in all). They are capable of sending stickers, videos, music, locations, documents and more.
Clients can display the results with vertical or horizontal scrolling, depending on the type of content:
As soon as the user taps on an item, it's immediately sent to the recipient, and the input field is cleared.
### Switching inline/PM modes
Some inline bots can benefit from an initial setup process, like connecting them to an account on an external service (e.g., YouTube). We've added an easy way of switching between the private chat with a bot and whatever chat the user wants to share inline results in.
You can display a special 'Switch to PM' button above the inline results (or instead of them). This button will open a private chat with the bot and pass a parameter of your choosing, so that you can prompt the user for the relevant setup actions. Once done, you can use an inline keyboard with a switch_inline_query button to send the user back to the original chat.
Sample bots@youtube – Shows a 'Sign in to YouTube' button, then suggests personalized results.
> Manual: Switch to PM
### Location-based results
Inline bots can request location data from their users. Use the /setinlinegeo command with @BotFather to enable this. Your bot will ask the user for permission to access their location whenever they send an inline request.
Sample bot@foursquare – This bot will ask for permission to access the user's location, then provide geo-targeted results.
### Spreading virally
Messages sent with the help of your bot will show its username next to the sender's name.
When a user taps on the bot username in the message header, the mention is automatically inserted into the input field. Entering the @ symbol in the input field brings up a list of suggestions, featuring recently used inline bots.
#### Collecting feedback
To know which of the provided results your users are sending to their chat partners, send @Botfather the /setinlinefeedback command. With this enabled, you will receive updates on the results chosen by your users.
Please note that this can create load issues for popular bots –  you may receive more results than actual requests due to caching (see the cache_time parameter in answerInlineQuery). For these cases, we recommend adjusting the probability setting to receive 1/10, 1/100 or 1/1000 of the results.
### Inline bot samples
Here are some sample inline bots, in case you’re curious to see one in action. Try any of these:@gif – GIF search@vid – Video search@pic – Yandex image search@bing – Bing image search@wiki – Wikipedia search@imdb – IMDB search@bold – Make bold, italic or fixed sys text
NEW@youtube - Connect your account for personalized results@music - Search and send classical music@foursquare – Find and send venue addresses@sticker – Find and send stickers based on emoji
