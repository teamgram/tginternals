# messages.sponsoredMessages
A set of sponsored messages associated to a channel

```
messages.sponsoredMessages#ffda656d flags:# posts_between:flags.0?int start_delay:flags.1?int between_delay:flags.2?int messages:Vector<SponsoredMessage> chats:Vector<Chat> users:Vector<User> = messages.SponsoredMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| posts_between | flags.0?int | If set, specifies the minimum number of messages between shown sponsored messages; otherwise, only one sponsored message must be shown after all ordinary messages. |
| start_delay | flags.1?int | For sponsored messages to show on channel videos », the number of seconds to wait before showing the first ad. |
| between_delay | flags.2?int | For sponsored messages to show on channel videos », the number of seconds to wait after the previous ad is hidden, before showing the next ad. |
| messages | Vector<SponsoredMessage> | Sponsored messages |
| chats | Vector<Chat> | Chats mentioned in the sponsored messages |
| users | Vector<User> | Users mentioned in the sponsored messages |


## Type
messages.SponsoredMessages

## Related pages
