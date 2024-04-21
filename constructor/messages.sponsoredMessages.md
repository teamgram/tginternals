# messages.sponsoredMessages
A set of sponsored messages associated to a channel

```
messages.sponsoredMessages#c9ee1d87 flags:# posts_between:flags.0?int messages:Vector<SponsoredMessage> chats:Vector<Chat> users:Vector<User> = messages.SponsoredMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| posts_between | flags.0?int | If set, specifies the minimum number of messages between shown sponsored messages; otherwise, only one sponsored message must be shown after all ordinary messages. |
| messages | Vector<SponsoredMessage> | Sponsored messages |
| chats | Vector<Chat> | Chats mentioned in the sponsored messages |
| users | Vector<User> | Users mentioned in the sponsored messages |


## Type
messages.SponsoredMessages

## Related pages
