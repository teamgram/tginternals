# updateMessageReactions
New message reactions » are available

```
updateMessageReactions#1e297bfa flags:# peer:Peer msg_id:int top_msg_id:flags.0?int saved_peer_id:flags.1?Peer reactions:MessageReactions = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | Peer | Peer |
| msg_id | int | Message ID |
| top_msg_id | flags.0?int | Forum topic ID |
| saved_peer_id | flags.1?Peer | If set, the reactions are in the specified monoforum topic ». |
| reactions | MessageReactions | Reactions |


## Type
Update

## Related pages
