# messages.preparedInlineMessage
Represents a prepared inline message received via a bot's mini app, that can be sent to some chats »

```
messages.preparedInlineMessage#ff57708d query_id:long result:BotInlineResult peer_types:Vector<InlineQueryPeerType> cache_time:int users:Vector<User> = messages.PreparedInlineMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| query_id | long | The query_id to pass to messages.sendInlineBotResult |
| result | BotInlineResult | The contents of the message, to be shown in a preview |
| peer_types | Vector<InlineQueryPeerType> | Types of chats where this message can be sent |
| cache_time | int | Caching validity of the results |
| users | Vector<User> | Users mentioned in the results |


## Type
messages.PreparedInlineMessage

## Related pages
