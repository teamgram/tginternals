# Bots FAQ

General

How do I create a bot?
Where can I get some code examples?
I have a feature request!
What messages will my bot get?
Why doesn't my bot see messages from other bots?

Getting Updates

How do I get updates?
Long polling problems
Webhook problems
Using self-signed certificates
How can I make sure webhook requests come from Telegram?

Handling Media

Downloading files
Uploading large files
Can I count of file_ids to be persistent?

Broadcasting to Users

How do I avoid hitting limits?
How do I message all my subscribers?
---
### General Questions
#### How do I create a bot?
Creating Telegram bots is super-easy, but you will need at least some skills at computer programming. In order for a bot to work, set up a bot account with @BotFather, then connect it to your backend server via our API.
Unfortunately, there are no out-of-the-box ways to create a working bot if you are not a developer. But we're sure you'll soon find plenty of bots created by other people to play with.
#### I'm a developer. Where can I find some examples?
Here are two sample bots, both written in PHP:
- Hello Bot demonstrates the basics of the Telegram bot API.
- Simple Poll bot is a more complete example, it supports both long-polling and Webhooks for updates.
> Many members of our community are building bots and publishing sources.We're collecting them on this page »
Ping us on @BotSupport if you've built a bot and would like to share it with others.
#### Will you add X to the Bot API?
The bot API is still pretty young. There are many potential features to consider and implement. We'll be studying what people do with their bots for a while to see which directions will be most important for the platform.
All bot developers are welcome to share ideas for our Bot API with our @BotSupport account.
#### What messages will my bot get?
1. All bots, regardless of settings, will receive:
- All service messages.
- All messages from private chats with users.
- All messages from channels where they are a member.
2. Bot admins and bots with privacy mode disabled will receive all messages except messages sent by other bots.
3. Bots with privacy mode enabled will receive:
- Commands explicitly meant for them (e.g., /command@this_bot).
- General commands from users (e.g. /start) if the bot was the last bot to send a message to the group.
- Messages sent via this bot.
- Replies to any messages implicitly or explicitly meant for this bot.
Note that each particular message can only be available to one privacy-enabled bot at a time, i.e., a reply to bot A containing an explicit command for bot B or sent via bot C will only be available to bot A. Replies have the highest priority.
#### Why doesn't my bot see messages from other bots?
Bots talking to each other could potentially get stuck in unwelcome loops. To avoid this, we decided that bots will not be able to see messages from other bots regardless of mode.
### Getting Updates
#### How do I get updates?
There are currently two ways of getting updates. You can either use long polling or Webhooks. Please note that it's not possible to get updates via long polling while an outgoing Webhook is set.
#### Long polling gives me the same updates again and again!
The getUpdates method returns the earliest 100 unconfirmed updates. To confirm an update, use the offset parameter when calling getUpdates like this:
All updates with update_id less than or equal to offset will be marked as confirmed on the server and will no longer be returned.
#### I'm having problems with Webhooks.
If you've set up your webhook successfully, but are not getting any updates, please remember:
- You need a valid SSL certificate for webhooks to work.
- To use a self-signed certificate, you need to upload your public key certificate using the certificate parameter in setWebhook. Please upload as InputFile, sending a String will not work.
- Ports currently supported for Webhooks: 443, 80, 88, 8443.
- Wildcard certificates may not be supported.
- Redirects are not supported.
- CN must exactly match your domain.
> Please check out this new WEBHOOK GUIDE to learn all there is to know about webhooks!
#### I'm having trouble with my self-signed certificate!
Please take a look at this self-signed certificate guide we made just for you. If you've read it and still have a question, ping us on botsupport.
#### How can I make sure that Webhook requests are coming from Telegram?
If you'd like to make sure that the Webhook request comes from Telegram, we recommend using a secret path in the URL you give us, e.g. www.example.com/your_token. Since nobody else knows your bot's token, you can be pretty sure it's us.
#### How can I make requests in response to updates?
This is possible if you're using webhooks. The upside is that you need less requests, the downside — that in this case it's not possible to know that such a request was successful or get its result.
Whenever you receive a webhook update, you have two options:
1. Issue POST to https://api.telegram.org/bot<token>/method
2. Reply directly and give method as JSON payload in the reply
> You may also want to look at our sample HelloBot, it offers a PHP implementation of this.
### Handling Media
#### How do I download files?
Use the getFile method. Please note that this will only work with files of up to 20 MB in size.
#### How do I upload a large file?
Bots can currently send files of any type of up to 50 MB in size, so yes, very large files won't work for now. Sorry. This limit may be changed in the future.
#### Can I count on file_ids to be persistent?
Yes, file_ids can be treated as persistent.
### Broadcasting to Users
#### My bot is hitting limits, how do I avoid this?
When sending messages inside a particular chat, avoid sending more than one message per second. We may allow short bursts that go over this limit, but eventually you'll begin receiving 429 errors.
If you're sending bulk notifications to multiple users, the API will not allow more than 30 messages per second or so. Consider spreading out notifications over large intervals of 8—12 hours for best results.
Also note that your bot will not be able to send more than 20 messages per minute to the same group.
#### How can I message all of my bot's subscribers at once?
Unfortunately, at this moment we don't have methods for sending bulk messages, e.g. notifications. We may add something along these lines in the future.
In order to avoid hitting our limits when sending out mass notifications, consider spreading them over longer intervals, e.g. 8-12 hours. The API will not allow bulk notifications to more than ~30 users per second, if you go over that, you'll start getting 429 errors.
See also: How to avoid hitting limits?
---
> If you've got questions that are not answered on this page, ping us at @BotSupport in Telegram.We welcome any suggestions for the Bot Platform and API.
