# updateDraftMessage
Notifies a change of a message draft.

```
updateDraftMessage#edfc111e flags:# peer:Peer top_msg_id:flags.0?int saved_peer_id:flags.1?Peer draft:DraftMessage = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | Peer | The peer to which the draft is associated |
| top_msg_id | flags.0?int | ID of the forum topic to which the draft is associated |
| saved_peer_id | flags.1?Peer | If set, the draft is related to the specified monoforum topic ID ». |
| draft | DraftMessage | The draft |


## Type
Update

## Related pages
