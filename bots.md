# Bots: An introduction for developers

Bots are small applications that run entirely within the Telegram app. Users interact with bots through flexible interfaces that can support any kind of task or service. For more information, see:

- Detailed Guide to Bot Features

- Full API Reference for Developers

- Basic Tutorial: From @BotFather to 'Hello World'

The Telegram Bot Platform hosts more than 10 million bots and is free for both users and developers.

### What Can You Do with Bots?

- Replace Entire Websites

- Natively Integrate AI Chatbots

- Manage Your Business

- Receive Payments

- Create Custom Tools

- Integrate with Services and Devices

- Host Games

- Build Social Networks

- Monetize Your Service

- Promote Your Project

- Anything Else!

#### Replace Entire Websites

Telegram bots can host Mini Apps built with JavaScript. This allows for infinitely flexible interfaces that can power everything from online stores to arcade games. Unlike websites, bots support seamless authorization and notifications through Telegram out of the box.

> Try @DurgerKingBot – or check out the dedicated guide to Mini Apps to build your own.

#### Natively Integrate AI Chatbots

Bots natively support threaded conversations to manage several different topics in parallel. This is especially useful for building AI chatbots — and lets users easily access information from previous chats.

Instead of waiting for full replies, chatbots can also stream live responses as they’re generated.

> You can easily enable topics in private chats by toggling on Threaded Mode via @BotFather.

> This feature is subject to an additional fee for Telegram Star purchases as described in Section 6.2.6 of our Terms of Service for Bot Developers.

#### Manage Your Business

Telegram Business users can connect Telegram bots to process and answer messages on their behalf, via their personal account. This allows businesses to seamlessly integrate any existing tools and workflows, or add new AI assistants to increase productivity.

As we continue to expand the set of free tools available to bots through this integration, we encourage all developers to innovate and develop useful applications and services for businesses on Telegram.

> Developers can turn on Business Mode in @BotFather if their bot supports integration with Telegram Business accounts.

##### Receive Payments

Bots can sell all kinds of goods and services on Telegram – to anyone in the world. Telegram Stars allow users to securely and effortlessly buy digital products via in-app purchases. In addition, physical products can be easily purchased through third-party providers that support integration with Mini Apps.

> Try @ShopBot – or check out our dedicated guides for digital and physical products to build your own.

#### Create Custom Tools

Increase your productivity by creating bots for specific tasks – like converting files, managing chats or fetching today’s forecast. Users can chat directly with bots, or add them to groups and channels to introduce extra features.

> Mini apps can generate media and files – that users can effortlessly share to other chats or a post as a story.

#### Integrate with Services and Devices

Mini apps can seamlessly integrate with third-party services, APIs and devices to instantly process and update information – like changing a user's emoji status when they start a game  or get in a taxi .

> By default, Mini Apps seamlessly integrate with Android and iOS, allowing users to add direct shortcuts to their device’s home screen.

Likewise, many popular platforms already have official Telegram bots, which allow users to comfortably access content in one app – or perform quick searches using inline mode.

> Try @GMailBot, @GitHubBot, @Bing, @YouTube, @wiki and more.

#### Host Games

Developers can create both lightweight HTML5 Games and immersive full-screen modern games with support for detailed motion controls, location-based points of interest and dynamic hardware optimizations.

> Try some of the games in the @Gamee library – or check out the HTML5 and Mini App manuals to build your own.

#### Build Social Networks

Bots can serve as an intermediary to connect users based on shared interests, location, and more. Coordinate meetups, show local services, or help people sell second-hand items.

> Users can place direct shortcuts to specific mini apps on the home screen of their devices – accessing services in one tap.

#### Monetize Your Service

Telegram offers a robust ecosystem of monetization features, allowing any bot to support its development with multiple revenue streams. Popular bots can passively earn income through Revenue Sharing from Telegram Ads, implement subscription plans for users – or offer paid content and digital products for Telegram Stars.

> Telegram Stars in your bot's balance can be used to increase message limits, send gifts to users or accept rewards in Toncoin.

#### Promote Your Project

Bots can host affiliate marketing programs – giving developers a transparent way to quickly scale with organic growth from user referrals.

Affiliate Programs support custom revenue sharing rates and variable commission periods, allowing you to customize your offers and update your campaign over time.

> To learn more and get started in just a few taps, check out our dedicated guide.

#### Anything Else

The possibilities for bots are endless – from simple scripts to complex mini apps. Whether you’re a beginner or professional programmer, you can create personalized tools with the help of the Bot Platform.

> All Mini Apps you build on Telegram can be highly customized to fit your brand identity, including by uploading high-quality media demos and setting a custom Loading Screen with your own logo and color palette

---

### How Do Bots Work?

> For a detailed explanation of Bot Features, see this guide

Telegram bots are special accounts that do not need a phone number to set up. Bots are connected to their owner’s server, which processes inputs and requests from users.

Telegram’s intermediary server handles all encryption and communication with the Telegram API. Developers communicate with this server via an easy HTTPS-interface with a simplified version of the Telegram API – known as the Bot API.

#### How Are Bots Different from Users?

Bots are able to process inputs and requests in ways that user accounts can’t, but there are several differences between a bot and a normal user.

- Bots don’t have ‘last seen’ or online statuses – instead they show a ‘bot’ label in the chat.

- Bots have limited cloud storage – older messages may be removed by the server shortly after they have been processed.

- Bots can't start conversations with users. A user must either add them to a group or send them a message first. People can search for your bot’s username or start a chat via its unique t.me/bot_username link.

- By default, bots added to groups only see relevant messages in the chat (see Privacy Mode).

- Bots never eat, sleep or complain (unless expressly programmed otherwise).

#### Bot Links

Bot usernames normally require a ‘bot’ suffix, but some bots don’t have them – such as @stickers, @gif, @wiki or @bing.

Anyone can assign collectible usernames to bots, including those without the 'bot' suffix.

### How Do I Create a Bot?

Creating Telegram bots is super-easy, but you will need at least some skills in computer programming.

Creating a bot is streamlined by Telegram’s Bot API, which gives the tools and framework required to integrate your code. To get started, message @BotFather on Telegram to register your bot and receive its authentication token.

> Your bot token is its unique identifier – store it in a secure place, and only share it with people who need direct access to the bot. Everyone who has your token will have full control over your bot.

#### What Next?

We recommend that you check out our guide to Bot Features to see what you can teach your bot to do:

- Detailed Guide to Bot Features

- Full API Reference for Developers

- Basic Tutorial: From @BotFather to 'Hello World'

- Code Examples

