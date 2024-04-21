# messages.channelMessages
Channel messages

```
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inexact | flags.1?true | If set, returned results may be inexact |
| pts | int | Event count after generation |
| count | int | Total number of results were found server-side (may not be all included here) |
| offset_id_offset | flags.2?int | Indicates the absolute position of messages[0] within the total result set with count count. This is useful, for example, if the result was fetched using offset_id, and we need to display a progress/total counter (like photo 134 of 200, for all media in a chat, we could simply use photo ${offset_id_offset} of ${count}. |
| messages | Vector<Message> | Found messages |
| topics | Vector<ForumTopic> | Forum topic information |
| chats | Vector<Chat> | Chats |
| users | Vector<User> | Users |


## Type
messages.Messages

## Related pages
