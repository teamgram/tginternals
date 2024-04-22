# Bot menu button

Bots can choose the behavior of the menu button shown next to the text input field.

For a simplified description using the HTTP bot API, see here ».

### Setting the menu button

Schema:

Bots can use bots.setBotMenuButton to change the menu button for a certain user, or for all users.

#### Set scope: all users

To change the menu button for all users use the following parameters:

- user_id - inputUserEmpty

- button - one of the following constructors:

- botMenuButton - Opens a bot mini app when clicked.

- botMenuButtonCommands - Opens the bot's command list when clicked.

botMenuButtonDefault shouldn't be used as it has no effect, keeping the previously set menu button (either botMenuButton or botMenuButtonCommands).

#### Set scope: specific users

To change the menu button for a specific user use the following parameters:

- user_id - inputUser with the user ID/access hash

- button - one of the following constructors:

- botMenuButton - Opens a bot mini app when clicked.

- botMenuButtonCommands - Opens the bot's command list when clicked.

- botMenuButtonDefault - Resets the behavior of the button to the default scope (all users).

### Getting the menu button

#### Bots

Bots might need to know the button type currently used in a given chat or in all chats: bots.getBotMenuButton can be used for this.

Users can't use this method, and should use the user method instead.

##### Get scope: all users

To get the menu button used for all users use the following parameter:

- user_id - inputUserEmpty

One of the following constructors will be returned:

- botMenuButton - Opens a bot mini app when clicked.

- botMenuButtonCommands - Opens the bot's command list when clicked.

botMenuButtonDefault will never be returned in this case.

##### Get scope: specific users

To get the menu button used for a specific user use the following parameter:

- user_id - inputUser with the user ID access/hash

One of the following constructors will be returned:

- botMenuButton - Opens a bot mini app when clicked.

- botMenuButtonCommands - Opens the bot's command list when clicked.

- botMenuButtonDefault - The default scope (all users) button behavior is in use.

#### Users

Users will receive an updateBotMenuButton update when a bot changes the behavior of the menu button globally or in the private chat with the user.

For new bots, users.getFullUser can be used to fetch the userFull related to the bot, containing the botInfo constructor with various info about the bot, including the menu button behavior.

botMenuButtonDefault will never be returned in a updateBotMenuButton or in a botInfo (but if it does happen, treat it like a botMenuButtonCommands).

Bots should use the bot method instead.

