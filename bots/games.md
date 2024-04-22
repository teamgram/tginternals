# Gaming Platform

Bots can offer their users HTML5 games to play solo or to compete against each other in groups and one-on-one chats. Games are a new type of content on Telegram that your bot can send to users.

> Check out the @gamebot and @gamee bots for examples of what you can do using the new Gaming Platform.

### Web Apps

Since April 2022, you can also use Web Apps to create powerful games using JavaScript.

> Check out the Web App Manual for details.

### Creating a Game

To get started, send the /newgame command to @BotFather.You will be prompted for a description text and a photo. You can also upload an optional GIF animation that demostrates your game to the users to make messages with the game more attractive (check out Lumberjack or Corsairs for examples).

### Launching the Game

Once the game is created, your bot can send it to chats as regular messages, or offer them via inline mode. The game message will always have an inline Play button.

When this button is pressed, your bot gets a callback query that indicates the requested game. You provide the correct URL for this particular user and the app automatically opens the game in the in-app browser.

### Adding Buttons

If you send the game message without any buttons, it will automatically have a 'Play GameName' button. You can manually add multiple buttons to your game message. Please note that the first button in the first row must always be the one that launches the game. You can add more buttons: e.g., for a description of the rules, or a button that links to the game's official community.

### Tracking High Scores

The message with your game will also display high scores for the current chat. When a new high score is set, a service message will be sent to the chat and the message with the current scoreboard will be updated. You can also request the necessary data for building in-game high score tables.

### Sharing Your Game to Telegram Chats

There are many way for users to spread your game virally if they like it. The interface will always have the standard system button for sharing the game in the top right corner:

You can also create an additional Share button inside your HTML page. Pressing this button will send the game to a desired chat along with the user's best score in the game.

To add the sharing button, include this script at the end of the <body> tag on your page:

Then use the method TelegramGameProxy.shareScore() to call the sharing option.

> Warning: Do not call this method without consent and direct action from the user.

Example:

This library will only work when launched from inside Telegram, so please don't use it on ordinary web pages.

### Using URL Parameters

If your URL is using a fragment identifier, please note that Telegram Apps could add certain service parameters to the fragment id. The names for such parameters will start in tg (you can check the code that adds them here). Use the TelegramGameProxy.initParams object if you need to read your own parameters from the fragment id.

### Creating a Great HTML5 Experience

Please make sure that your HTML5 page is responsive and works well on all Telegram apps and supported platforms. If you find it impossible to support certain conditions or platforms, don't leave your users hanging and at least provide a notification.

> See the Bot API Manual for the relevant methods and objects.

