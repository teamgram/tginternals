# messages.messagesSlice
Incomplete list of messages and auxiliary data.

```
messages.messagesSlice#3a54685e flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inexact | flags.1?true | If set, indicates that the results may be inexact |
| count | int | Total number of messages in the list |
| next_rate | flags.0?int | Rate to use in the offset_rate parameter in the next call to messages.searchGlobal |
| offset_id_offset | flags.2?int | Indicates the absolute position of messages[0] within the total result set with count count. This is useful, for example, if the result was fetched using offset_id, and we need to display a progress/total counter (like photo 134 of 200, for all media in a chat, we could simply use photo ${offset_id_offset} of ${count}. |
| messages | Vector<Message> | List of messages |
| chats | Vector<Chat> | List of chats mentioned in messages |
| users | Vector<User> | List of users mentioned in messages and chats |


## Type
messages.Messages

## Related pages
