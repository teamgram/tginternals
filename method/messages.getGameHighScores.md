# messages.getGameHighScores
Get highscores of a game

```
messages.highScores#9a3bfd99 scores:Vector<HighScore> users:Vector<User> = messages.HighScores;
---functions---
messages.getGameHighScores#e822649d peer:InputPeer id:int user_id:InputUser = messages.HighScores;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Where was the game sent |
| id | int | ID of message with game media attachment |
| user_id | InputUser | Get high scores made by a certain user |


## Result
messages.HighScores

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |

