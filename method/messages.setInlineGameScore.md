# messages.setInlineGameScore
Use this method to set the score of the specified user in a game sent as an inline message (bots only).

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setInlineGameScore#15ad9f64 flags:# edit_message:flags.0?true force:flags.1?true id:InputBotInlineMessageID user_id:InputUser score:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| edit_message | flags.0?true | Set this flag if the game message should be automatically edited to include the current scoreboard |
| force | flags.1?true | Set this flag if the high score is allowed to decrease. This can be useful when fixing mistakes or banning cheaters |
| id | InputBotInlineMessageID | ID of the inline message |
| user_id | InputUser | User identifier |
| score | int | New score |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |

