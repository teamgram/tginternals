# Commands

Bots offer a set of commands that can be used by users in private, or in a chat.

For a simplified description using the HTTP bot API, see here ».

### Getting commands

The botInfo constructors contained in the userFull, chatFull, channelFull contain a list of commands, and for groups, the ID and a description of each bot.

In graphical clients, when users begin a message with a /, a list of commands supported by all bots present in the current chat should be shown; the same should be done for one-to-one chats with the bot itself.

If the command list of a bot changes, the bot_info_version contained in the user constructor received in updates will change; this indicates that the client should refetch full bot information using users.getFullUser.

### Setting commands

The command list can be changed by the owner of the bot through @botfather, but bots can also change their own command list by invoking bots.setBotCommands.

