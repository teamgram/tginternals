# Games

Bots can offer users HTML5 games to play solo or to compete against each other in groups and one-on-one chats.

### Sending a game

Bots can directly send a game using messages.sendMedia, providing:

- The game's short name obtained from @BotFather or from a game link » to inputGameShortName.short_name

- The current bot's info to inputGameShortName.bot_id

The sent message will contain a messageMediaGame with a game, that can then be used by users to forward the game using sendMedia with inputGameID.

### Starting a game

Games are started clicking on the button, which triggers an callback query that returns the game URL, for more info see here ».
The game should then be opened in a WebView or in native UI (specified by the native_ui flag), exposing the appropriate HTML5 APIs in order to receive various JS game events directly from the code of the game, as described here ».

### Setting highscores

Games are supposed to report back to the MTProto API every time the user looses a game with a new highscore.
Since games run in the browser, they cannot directly report data to the API using the bot token, which must be kept secret.
Instead, they should send highscores to an intermediate server, that will then report scores using messages.setGameScore or messages.setInlineGameScore, depending on the source of the game.

- The edit_message flag should be set if the game message should be automatically edited to include the current scoreboard

- The force flag should be set if the high score is allowed to decrease. This can be useful when fixing mistakes or banning cheaters.

### Getting highscores

Every time a highscore is reached, and the edit_message flag is set when reporting the score, a messageService with a messageActionGameScore is generated, indicating that the highscore of a certain game has changed, thanks to a certain user_id.
Our own current position of the scoreboard is also reported as pos.

When receiving such an update, graphical clients should refetch the scoreboard using messages.getGameHighScores or messages.getInlineGameHighScores.

