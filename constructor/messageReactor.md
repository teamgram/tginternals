# messageReactor
Info about a user in the paid Star reactions leaderboard for a message.

```
messageReactor#4ba3a95a flags:# top:flags.0?true my:flags.1?true anonymous:flags.2?true peer_id:flags.3?Peer count:int = MessageReactor;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| top | flags.0?true | If set, the reactor is one of the most active reactors; may be unset if the reactor is the current user. |
| my | flags.1?true | If set, this reactor is the current user. |
| anonymous | flags.2?true | If set, the reactor is anonymous. |
| peer_id | flags.3?Peer | Identifier of the peer that reacted: may be unset for anonymous reactors different from the current user (i.e. if the current user sent an anonymous reaction anonymous will be set but this field will also be set). |
| count | int | The number of sent Telegram Stars. |


## Type
MessageReactor

## Related pages
