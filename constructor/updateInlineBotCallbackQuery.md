# updateInlineBotCallbackQuery
This notification is received by bots when a button is pressed

```
updateInlineBotCallbackQuery#691e9052 flags:# query_id:long user_id:long msg_id:InputBotInlineMessageID chat_instance:long data:flags.0?bytes game_short_name:flags.1?string = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query_id | long | Query ID |
| user_id | long | ID of the user that pressed the button |
| msg_id | InputBotInlineMessageID | ID of the inline message with the button |
| chat_instance | long | Global identifier, uniquely corresponding to the chat to which the message with the callback button was sent. Useful for high scores in games. |
| data | flags.0?bytes | Data associated with the callback button. Be aware that a bad client can send arbitrary data in this field. |
| game_short_name | flags.1?string | Short name of a Game to be returned, serves as the unique identifier for the game |


## Type
Update

## Related pages
