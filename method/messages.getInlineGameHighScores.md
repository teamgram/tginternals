# messages.getInlineGameHighScores
Get highscores of a game sent using an inline bot

```
messages.highScores#9a3bfd99 scores:Vector<HighScore> users:Vector<User> = messages.HighScores;
---functions---
messages.getInlineGameHighScores#f635e1b id:InputBotInlineMessageID user_id:InputUser = messages.HighScores;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | InputBotInlineMessageID | ID of inline message |
| user_id | InputUser | Get high scores of a certain user |


## Result
messages.HighScores

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |

