# stats.publicForwards
Contains info about the forwards of a story as a message to public chats and reposts by public channels.

```
stats.publicForwards#93037e20 flags:# count:int forwards:Vector<PublicForward> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stats.PublicForwards;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| count | int | Total number of results |
| forwards | Vector<PublicForward> | Info about the forwards of a story. |
| next_offset | flags.0?string | Offset used for pagination. |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |


## Type
stats.PublicForwards

## Related pages
