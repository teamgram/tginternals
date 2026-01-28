# messages.savePreparedInlineMessage
Save a prepared inline message, to be shared by the user of the mini app using a web_app_send_prepared_message event

```
messages.botPreparedInlineMessage#8ecf0511 id:string expire_date:int = messages.BotPreparedInlineMessage;
---functions---
messages.savePreparedInlineMessage#f21f7f2f flags:# result:InputBotInlineResult user_id:InputUser peer_types:flags.0?Vector<InlineQueryPeerType> = messages.BotPreparedInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| result | InputBotInlineResult | The message |
| user_id | InputUser | The user to whom the web_app_send_prepared_message event event will be sent |
| peer_types | flags.0?Vector<InlineQueryPeerType> | Types of chats where this message can be sent |


## Result
messages.BotPreparedInlineMessage

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | RESULT_ID_INVALID | One of the specified result IDs is invalid. |
| 400 | SEND_MESSAGE_GAME_INVALID | An inputBotInlineMessageGame can only be contained in an inputBotInlineResultGame, not in an inputBotInlineResult/inputBotInlineResultPhoto/etc. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

