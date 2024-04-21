# updateShortChatMessage
Shortened constructor containing info on one new incoming text message from a chat

```
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| out | flags.1?true | Whether the message is outgoing |
| mentioned | flags.4?true | Whether we were mentioned in this message |
| media_unread | flags.5?true | Whether the message contains some unread mentions |
| silent | flags.13?true | If true, the message is a silent message, no notifications should be triggered |
| id | int | ID of the message |
| from_id | long | ID of the sender of the message |
| chat_id | long | ID of the chat where the message was sent |
| message | string | Message |
| pts | int | PTS |
| pts_count | int | PTS count |
| date | int | date |
| fwd_from | flags.2?MessageFwdHeader | Info about a forwarded message |
| via_bot_id | flags.11?long | Info about the inline bot used to generate this message |
| reply_to | flags.3?MessageReplyHeader | Reply (thread) information |
| entities | flags.7?Vector<MessageEntity> | Entities for styled text |
| ttl_period | flags.25?int | Time To Live of the message, once updateShortChatMessage.date+updateShortChatMessage.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. |


## Type
Updates

## Related pages
