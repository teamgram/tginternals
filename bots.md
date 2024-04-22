# Bots: An introduction for developers

Bots are small applications that run entirely within the Telegram app. Users interact with bots through flexible interfaces that can support any kind of task or service. For more information, see:

- Detailed Guide to Bot Features

- Full API Reference for Developers

- Basic Tutorial: From @BotFather to 'Hello World'

The Telegram Bot Platform hosts more than 10 million bots and is free for both users and developers.

### What Can You Do with Bots?

- Replace Entire Websites

- Manage Your Business

- Receive Payments

- Create Custom Tools

- Integrate with Other Services

- Host Games

- Build Social Networks

- Anything Else!

#### Replace Entire Websites

Telegram bots can host Mini Apps built with JavaScript. This allows for infinitely flexible interfaces that can power everything from online stores to arcade games. Unlike websites, bots support seamless authorization and notifications through Telegram out of the box.

> Try @DurgerKingBot – or check out the dedicated guide to Web Apps to build your own.

#### Manage Your Business

Telegram Business users can connect Telegram bots to process and answer messages on their behalf, via their personal account. This allows businesses to seamlessly integrate any existing tools and workflows, or add new AI assistants to increase productivity.

As we continue to expand the set of free tools available to bots through this integration, we encourage all developers to innovate and develop useful applications and services for businesses on Telegram.

> Developers can turn on Business Mode in @BotFather if their bot supports integration with Telegram Business accounts.

#### Receive Payments

Bots can receive payments from more than 200 countries through more than 20 integrated payment providers (which include support for Apple Pay and Google Pay). These payments are securely processed by the providers and Telegram takes no commission.

> Try @ShopBot – or check out the Bot Payments Manual to build your own.

#### Create Custom Tools

Increase your productivity by creating bots for specific tasks – like converting files, managing chats or fetching today’s forecast. Users can chat directly with bots, or add them to groups and channels to introduce extra features.

> Try @QuizBot to combine several quiz-style polls into a proper quiz.

#### Integrate with Other Services

Many popular platforms already have official Telegram bots, which allow users to comfortably access content in one app – or perform quick searches using inline mode.

> Try @GMailBot, @GitHubBot, @Bing, @YouTube, @wiki and more.

#### Host Games

Using HTML5, developers can create immersive single or multi-player games that allow users to team up or compete for the highest score.

> Try @Gamee and @GameBot – or check out the HTML5 Games Manual to build your own.

#### Build Social Networks

Bots can serve as an intermediary to connect users based on shared interests, location, and more. Coordinate meetups, show local services, or help people sell second-hand items.

#### Anything Else

The possibilities for bots are endless – from simple scripts to complex mini apps. Whether you’re a beginner or professional programmer, you can create personalized tools with the help of the Bot Platform.

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

