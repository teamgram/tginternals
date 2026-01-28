# updateBusinessBotCallbackQuery
A callback button sent via a business connection was pressed, and the button data was sent to the bot that created the button.

```
updateBusinessBotCallbackQuery#1ea2fda7 flags:# query_id:long user_id:long connection_id:string message:Message reply_to_message:flags.2?Message chat_instance:long data:flags.0?bytes = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query_id | long | Query ID |
| user_id | long | ID of the user that pressed the button |
| connection_id | string | Business connection ID |
| message | Message | Message that contains the keyboard (also contains info about the chat where the message was sent). |
| reply_to_message | flags.2?Message | The message that message is replying to. |
| chat_instance | long | Global identifier, uniquely corresponding to the chat to which the message with the callback button was sent. Useful for high scores in games. |
| data | flags.0?bytes | Callback data |


## Type
Update

## Related pages
