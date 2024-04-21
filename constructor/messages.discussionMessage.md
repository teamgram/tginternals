# messages.discussionMessage
Information about a message thread

```
messages.discussionMessage#a6341782 flags:# messages:Vector<Message> max_id:flags.0?int read_inbox_max_id:flags.1?int read_outbox_max_id:flags.2?int unread_count:int chats:Vector<Chat> users:Vector<User> = messages.DiscussionMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| messages | Vector<Message> | The messages from which the thread starts. The messages are returned in reverse chronological order (i.e., in order of decreasing message ID). |
| max_id | flags.0?int | Message ID of latest reply in this thread |
| read_inbox_max_id | flags.1?int | Message ID of latest read incoming message in this thread |
| read_outbox_max_id | flags.2?int | Message ID of latest read outgoing message in this thread |
| unread_count | int | Number of unread messages |
| chats | Vector<Chat> | Chats mentioned in constructor |
| users | Vector<User> | Users mentioned in constructor |


## Type
messages.DiscussionMessage

## Related pages
