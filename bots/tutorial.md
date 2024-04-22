# From BotFather to 'Hello World'

This guide will walk you through everything you need to know to build your first Telegram Bot.If you already know your way around some of the basic steps, you can jump directly to the part you're missing. Equivalent examples are available in C#, Python, Go and TypeScript .

- Introduction

- Basic Tutorial

- Advanced Tutorial

- Further Reading

---

### Introduction

At its core, you can think of the Telegram Bot API as software that provides JSON-encoded responses to your queries.

A bot, on the other hand, is essentially a routine, software or script that queries the API by means of an HTTPS request and waits for a response. There are several types of requests you can make, as well as many different objects that you can use and receive as responses.

Since your browser is capable of sending HTTPS requests, you can use it to quickly try out the API. After obtaining your token, try pasting this string into your browser:

In theory, you could interact with the API with basic requests like this, either via your browser or other tailor-made tools like cURL. While this can work for simple requests like the example above, it's not practical for larger applications and doesn't scale well.For that reason, this guide will show you how to use libraries and frameworks, along with some basic programming skills, to build a more robust and scalable project.

If you know how to code, you'll fly right through each step in no time – and if you're just starting out, this guide will show you everything you need to learn.

> We will use Java throughout this guide as it's one of the most popular programming languages, however, you can follow along with any language as all the steps are fundamentally the same.Since Java is fully cross-platform, each code example will work with any operating system.If you pick another language, equivalent examples are available in C#, Python, Go and TypeScript .

### Getting Ready

First, we will briefly cover how to create your first project, obtain your API token and download all necessary dependencies and libraries.

For the purposes of this guide, a copy of the bot you will be creating is also live at @TutorialBot – feel free to check it out along the way to see how your own implementation should look after each step.

#### Obtain Your Bot Token

In this context, a token is a string that authenticates your bot (not your account) on the bot API. Each bot has a unique token which can also be revoked at any time via @BotFather.

Obtaining a token is as simple as contacting @BotFather, issuing the /newbot command and following the steps until you're given a new token. You can find a step-by-step guide here.

Your token will look something like this:

> Make sure to save your token in a secure place, treat it like a password and don't share it with anyone.

#### Download an IDE

To program in Java you'll need an IDE – a special text editor that will let you write, compile and run your code.In this tutorial, we'll use IntelliJ – there are several free, open source alternatives like Eclipse or NetBeans which work in the exact same way.

You will also need a JDK, a software kit that allows your Java code to run.Most IDEs don't include a JDK, so you should download a version compatible with your operating system separately. You can find a free, open source version here.

> If you use another language, the steps are identical. You will just have to download a different IDE and software development kit.

#### Pick a Framework or Library

You can think of a framework as software that handles all the low-level logic for you, including the API calls, and lets you focus on your bot-specific logic.

In this tutorial, we'll use TelegramBots, but you can follow along with any equivalent implementation, since all the underlying methods are either similar or exactly the same.

> You can find many frameworks, along with code examples, in our dedicated list.

#### Create Your Project

In IntelliJ, go to File > New > Project.

Fill in the fields accordingly:

- Name - The name of your project. For example, BotTutorial.

- Location - Where to store your project. You can use the default value.

- Language - Java

- Build System - The framework that will handle your dependencies. Pick Maven.

- JDK - Pick whichever version you downloaded. We'll be using version 17.

- Add Sample Code - Leave this selected, it will generate some needed files for you.

- Advanced Settings > GroupId - We suggest tutorial.

- Advanced Settings > ArtifactId - You can use the default value.

After hitting Create, if you did everything correctly, your Project view in the top left should show a project structure along these lines:

> Other IDEs will follow a similar pattern. Your dependency management system will have a different name (or no name at all if it's built-in) depending on the language you chose.

If this looks scary, don't worry. We will only be using the Main file and the pom.xml file.In fact, to check that everything is working so far, double click on Main and click on the small green arrow on the left of public class Main, then select the first option.If you followed the steps correctly, Hello world! should appear in the console below.

#### Add Framework Dependency

We will now instruct the IDE to download and configure everything needed to work with the API.This is very easy and happens automatically behind the scenes.

First, locate your pom.xml file on the left side of the screen.Open it by double-clicking and simply add:

right after the </properties> tag.

When you're done, your pom.xml should look something like this.

### Start Coding

We are ready to start coding. If you're a beginner, consider that being familiar with your language of choice will greatly help. With this tutorial, you'll be able to teach your bot basic behaviors, though more advanced features will require some coding experience.

#### Creating a Bot Class

If you're familiar with object-oriented programming, you'll know what a class is.If you've never heard of it before, consider a class as a file where you write some logic.

To create the class that will contain the bot logic, right click on tutorial from the project tree on the left and select New > Java Class. Name it Bot and hit enter.

Now we have to connect this class to the bot framework. In other words, we must make sure it extends TelegramLongPollingBot. To do that, just add extends TelegramLongPollingBot right after Bot.A red line will appear – it simply means we're missing some important methods.

To fix this, hover over the red line, click on implement methods, then hit OK.Depending on the IDE, this option may be called implement missing methods or something similar.

You should end up with this – if something went wrong, feel free to copy it from here and paste it in your class:

> If you get a red line under TelegramLongPollingBot, it means you didn't set up your pom.xml correctly. If this is the case, restart from here.

#### Available Methods

Let's look into these 3 methods one by one.

- getBotUsername - This method must be edited to always return your bot's username. You should replace the null return value with it.

- getBotToken - This method will be used by the framework to retrieve your bot token. You should replace the null return value with the token.

- onUpdateReceived - This is the most important method. It will be called automatically whenever a new Update is available. Let's add a System.out.println(update); call in there to quickly show what we are getting.

After you've replaced all the strings, you should end up with this:

At this point, the bot is configured and ready to go – time to register it on the API and start processing updates.

> In the future, you should consider storing your token in a dedicated settings file or in environment variables. Keeping it in the code is fine for the scope of this tutorial, however, it's not very versatile and is generally considered bad practice.

#### Registering the Bot

To register the bot on the API, simply add a couple of lines in the main method that will launch the application. If you named your class Bot, this is what your main method should look like:

> You can place this method in any class. Since we have an auto-generated main method in the Main class, we'll be using that one for this tutorial.

### First Run

It's time to run your bot for the first time.Hit the green arrow to the left of public static void main and select the first option.

And then there was nothing. Yes, a bit anticlimactic.This is because your bot has nothing to print – there are no new updates because nobody messaged it yet.

If you try messaging the bot on Telegram, you'll then see new updates pop up in the console. At this point, you have your very own Telegram Bot – quite the achievement. Now, on to making it a bit more intelligent.

> If nothing pops up, make sure you messaged the right bot and that the token you pasted in the code is correct.

### Receiving Messages

Every time someone sends a private message to your bot, your onUpdateReceived method will be called automatically and you'll be able to handle the update parameter, which contains the message, along with a great deal of other info which you can see detailed here.

Let's focus on two values for now:

- The user - Who sent the message. Access it via update.getMessage().getFrom().

- The message - What was sent. Access it via update.getMessage().

Knowing this, we can make it a bit more clear in the console output.

This is just a basic example – you can now play around with all the methods to see everything you can pull out of these objects. You can try getUsername, getLanguageCode, and dozens more.

Knowing how to receive, process and print incoming messages, now it's time to learn how to answer them.

> Remember to stop and re-launch your bot after each change to the code.

### Sending Messages

To send a private text message, you generally need three things:

- The user must have contacted your bot first. (Unless the user sent a join request to a group where your bot is an admin, but that's a more advanced scenario).

- You must have previously saved the User ID (user.getId())

- A String object containing the message text, 1-4096 characters.

With that out of the way, let's create a new method to send the first message:

And proceed to run this in the main method, right after registering the bot.For this example, we'll assume your User ID is 1234.

If you did everything correctly, your bot should text you Hello World! every time you launch your code. Sending messages to groups or channels – assuming you have the relevant permissions – is as simple as replacing 1234 with the ID of the respective chat.

> Try experimenting with other types of messages, like SendPhoto, SendSticker, SendDice…A full list is available starting here.

### Echo Bot

Let's practice everything we tried so far by coding an Echo Bot.Its functionality will be rather simple: every text message it receives will be sent right back to the user.

#### Copying Text

The most intuitive way of coding this is saving the User ID and calling sendText right after each update.

In other words:

This works for text but can be extended to stickers, media and files.

#### Copying Everything

There are more specific functions that can be used to copy messages and send them back.Let's build a method to do just that:

After replacing the method call inonUpdateReceived, running the code will result in a fully functional Echo Bot.

> This tutorial assumes that updates always contain messages for the sake of simplicity. This may not always be true – be sure to implement all the proper checks in your code to handle every type of update with the appropriate methods.

### Executing Commands

To learn what a command is and how it works, we recommend reading this dedicated summary.In this guide, we'll focus on the technical side of things.

#### Creating Your Command

Begin by opening @BotFather.Type /mybots > Your_Bot_Name > Edit Bot > Edit Commands.

Now send a new command, followed by a brief description.For the purpose of this tutorial, we'll implement two simple commands:

#### Command Logic

We want the Echo Bot to reply in uppercase when it's in scream mode and normally otherwise.

First, let's create a variable to store the current mode.

Then, let's change some logic to account for this mode.

Finally, let's add a couple more lines to the onUpdateReceived method to process each command before replying.

As you can see, it checks if the message is a command. If it is, the bot enters scream mode.In the update method, we check which mode we are in and either copy the message or convert it to upper case before sending it back.

And that's it. Now the bot can execute commands and change its behavior accordingly.

Naturally, this simplified logic will change the bot's behavior for everyone – not just the person who sent the command. This can be fun for this tutorial but won't work in a production environment – consider using a Map, dictionary or equivalent data structure to assign settings for individual users.

> Remember to always implement a few basic global commands.You can practice by implementing a simple feedback to the /start command, which we intentionally left out.

### Buttons and Keyboards

To streamline and simplify user interaction with your bot, you can replace many text-based exchanges with handy buttons. These buttons can perform a wide variety of actions and can be customized for each user.

#### Button Types

There are two main types of buttons:

- Reply Buttons - used to provide a list of predefined text reply options.

- Inline Buttons - used to offer quick navigation, shortcuts, URLs, games and so much more.

Using these buttons is as easy as attaching a ReplyKeyboardMarkup or an InlineKeyboardMarkup to your SendMessage object.

This guide will focus on inline buttons since they only require a few extra lines of code.

#### Creating Buttons

First of all, let's create some buttons.

Let's go back through the fields we specified:

- Text - This is what the user will see, the text that appears on the button

- Callback Data - This will be sent back to the code instance as part of a new Update, so we can quickly identify what button was clicked.

- Url - A button that specifies a URL doesn't specify callbackdata since its behavior is predefined – it will open the given link when tapped.

#### Creating Keyboards

The buttons we created can be assembled into two keyboards, which will then be used to navigate back and forth between two sample menus.

First, add two fields to store the necessary keyboards.

Then, build and assign them.

> You can place this code wherever you prefer, the important thing is making sure that keyboard variables are accessible from the method call that will send the new menu. If you're confused by this concept and don't know where to put them, just paste them above the command processing flow.

#### Sending Keyboards

Sending a keyboard only requires specifying a reply markup for the message.

> You may have noticed that we also added a new parameter, HTML.This is called a formatting option and will allow us to use HTML tags and add formatting to the text later on.

#### Menu Trigger

We could send a new menu for each new user, but for simplicity let's add a new command that will spawn a menu. We can achieve this by adding a new else clause to the previous command flow.

Try sending /menu to your bot now. If you did everything correctly, you should see a brand new menu pop up.

> In a production environment, commands should be handled with an appropriate design pattern that isolates them into different executor classes – modular and separated from the main logic.

### Navigation

When building complex bots, navigation is essential. Your users must be able to move seamlessly from one menu to the next.

In this example, we want the Next button to lead the user to the second menu.The Back button will send us back.To do that, we will start processing incoming CallbackQueries, which are the results we get after the user taps on a button.

A CallbackQuery is essentially composed of three main parameters:

- queryId - Needed to close the query. You must always close new queries after processing them – if you don't, a loading symbol will keep showing on the user's side on top of each button.

- data - This identifies which button was pressed.

- from - The user who pressed the button.

Processing in this context just means executing the action uniquely identified by the button, then closing the query.

A very basic button handler could look something like:

With this handler, whenever a button is tapped, your bot will automatically navigate between inline menus.Expanding on this concept allows for endless combinations of navigable submenus, settings and dynamic pages.

### Database

Telegram does not host an update database for you – once you process and consume an update, it will no longer be available. This means that features like user lists, message lists, current user inline menu, settings, etc. have to be implemented and maintained by bot developers.

If your bot needs one of these features and you want to get started on data persistence, we recommend that you look into serialization practices and libraries for your language of choice, as well as available databases.

Implementing a database is out of scope for this guide, however, several guides are available online for simple embedded open source software solutions like SQLite, HyperSQL, Derby and many more.

> Your language of choice will also influence which databases are available and supported – the list above assumes you followed this Java tutorial.

### Hosting

So far, your bot has been running on your local machine – your PC. While this may be good for developing, testing and debugging, it is not ideal for a production environment.You'll want your bot to be available and responsive at all times, but your computer might not always be online.

This can be done in four steps:

- Package your codeMaking your bot easy to move and runnable outside of an IDE is essential to host it elsewhere.If you followed this tutorial, this standard guide will work for you. If you didn't, look into export or packaging guides for your IDE and language of choice – procedures may vary but the end result is the same.

- Purchase a VPS or equivalent serviceA server is essentially a machine that is always online and running, without you having to worry about anything. To host your bot, you can opt for a VPS which serves this purpose and can be rented from several different providers.Another option would be to purchase a network-capable microcontroller, which come in all different specs and sizes depending on your needs.

> You should ensure that all user data remains heavily encrypted at all times in your database to guarantee the privacy of your users. The same concept applies to your local instance, however, this becomes especially important once you transfer your database to a remote server.

- Upload your executable/package

Once you have a working ssh connection between your machine and your new server, you should upload your executable and all associated files.We will assume the runnable jar TutorialBot.jar and its database dbase.db are currently in the /TBot folder.

- Run your application

Depending on which language you chose, you might have to configure your server environment differently. If you chose Java, you just need to install a compatible JDK.

If you did everything correctly, you should see a Java version as the output, along with a few other values. This means you're ready to run your application.

Now, to run the executable:

Your bot is now online and users can interact with it at any time.

> To streamline and modularize this process, you could employ a specialized docker container or equivalent service.If you followed along in one of the equivalent examples (C#, Python, Go and TypeScript) you can find a detailed set of instructions to export and run your code here.

### Further Reading

If you got this far, you might be interested in these additional guides and docs:

- General Bot Platform Overview

- Detailed List of Bot Features

- Full API Reference

If you encounter any issues while following this guide, you can contact us on Telegram at @BotSupport.

