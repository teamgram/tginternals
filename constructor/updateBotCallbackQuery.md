# updateBotCallbackQuery
A callback button was pressed, and the button data was sent to the bot that created the button

```
updateBotCallbackQuery#b9cfc48d flags:# query_id:long user_id:long peer:Peer msg_id:int chat_instance:long data:flags.0?bytes game_short_name:flags.1?string = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query_id | long | Query ID |
| user_id | long | ID of the user that pressed the button |
| peer | Peer | Chat where the inline keyboard was sent |
| msg_id | int | Message ID |
| chat_instance | long | Global identifier, uniquely corresponding to the chat to which the message with the callback button was sent. Useful for high scores in games. |
| data | flags.0?bytes | Callback data |
| game_short_name | flags.1?string | Short name of a Game to be returned, serves as the unique identifier for the game |


## Type
Update

## Related pages
