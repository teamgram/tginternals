# Introducing Bot API 2.0

> Howdy! This text assumes that you‘re familiar with Telegram’s bot platform.If this is not the case, kindly check out our Introduction to Bots.

Today we‘re introducing the biggest change to Telegram’s Bot Platform since June 2015. These new tools will help you create fluid and intuitive interfaces for your bots. And bots  are becoming a lot more capable. They can now send any type of content supported on Telegram, provide location-based services and integrate with other services deeply based on users' phone numbers.

If you'd like a more concise changelog, you can find one in the Bot API Manual.

### New Inline Keyboards

To begin with, we're adding a new type of keyboard that is integrated directly into the message it belongs to. Inline keyboards are available for messages sent both in chat mode and inline mode.

Unlike with custom reply keyboards, pressing buttons on inline keyboards doesn't result in messages sent to the chat. Instead, inline keyboards support buttons that work behind the scenes: callback buttons, URL buttons and switch to inline buttons.

> Manual: Inline keyboards »

#### Callback buttons

When a user presses a callback button, no messages are sent to the chat. Instead, your bot simply receives the relevant query. Upon receiving the query, your bot can display some result in a notification at the top of the chat screen or in an alert.

Sample bot@music – This sample music bot uses inline callback buttons to flip pages and reload random results.

Read on to updating messages to find out how callback buttons can get even cooler.

#### URL buttons

Buttons of this type have a small arrow icon to help the user understand that tapping on a URL button will open an external link. Naturally, we'll show them a confirmation alert before opening the link in the browser.

#### Switch to Inline buttons

Pressing a switch to inline button prompts the user to select a chat, opens it and inserts the bot's username into the input field. You can also pass a query that will be inserted along with the username – this way your users will immediately get some inline results they can share.

Sample bot@sticker – This sticker search bot offers a ‘switch to inline’ button to teach users how to use it in inline mode.

### Updating Messages

Since inline keyboards don‘t send additional messages to the chat, it made sense to give bots a way of manipulating their existing messages, so that they don’t have to send a new message each time they need to update something. This helps reduce clutter and build more fluid interfaces.

Sample bot@music – Watch how the music bot updates its messages with search results when you press the navigation buttons.

> Manual: Updating messages »

### Locations and Numbers

Some bots need extra data from the user to work properly. For example, knowing the user‘s location helps provide more relevant geo-specific results. The user’s phone number can be very useful for integrations with other services, like banks, etc.

We've added an easy way for bots to ask the user for their location and phone number using special buttons. Note that both phone number and location request buttons will only work in private chats.

When these buttons are pressed, Telegram clients will display a confirmation alert that tells the user what's about to happen.

> Manual: Number and location buttons »

Inline bots can also request location data from their users. Use the /setinlinegeo command with @BotFather to enable this. Your bot will ask the user for permission to access their location whenever they send an inline request.

Sample bot@foursquare – This bot will ask for permission to access the user's location, then provide geo-targeted results.

### Inline Bots 2.0

Speaking of inline bots, they are also getting a major upgrade today.

#### New types of content

Inline bots now support all types of content available in Telegram (19 in all), they are now capable of sending stickers, videos, music, locations, documents and more.

Sample bots@sticker – This sticker bot will accept one or more emoji and search for relevant stickers.@music – The music bot allows users to send mp3 tracks from a database of public domain classical music.

> Manual: Types of inline content »

#### Switching between inline mode and private chat

Some inline bots can benefit from an initial setup process, like connecting them to an account on an external service (e.g., YouTube). We've added an easy way of switching between the private chat with a bot and whatever chat the user wants to share inline results in.

You can now display a special ‘Switch to PM’ button above the inline results (or instead of them). This button will open a private chat with the bot and pass a parameter of your choosing, so that you can prompt the user for the relevant setup actions. Once done, you can use an inline keyboard with a switch_inline_query button to send the user back to the original chat.

Sample bots@youtube – Shows a ‘Sign in to YouTube’ button, then suggests personalized results.

> Manual: Switch to PM

#### Better inline UI

Since sending content via inline bots works differently from sending ordinary messages, we‘ve changed the interface a little. There’s hardly a more effective way of explaining that there‘s no need to hit ’Send':

Tapping on the cross icon once will clear the query, tapping twice will give the ‘Send’ button back to the user.

### Group Admins

As a dessert, we‘re beginning to roll out tools that will allow you to create bot solutions for group admins. As the first step, we’ve added methods to remove members from groups and supergroups.

> Manual: Group management »

And that's about it for now. Stay tuned for more updates and subscribe to our official @Botnews channel on Telegram.

> Read the full changelog for this update »

