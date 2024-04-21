# updateDraftMessage
Notifies a change of a message draft.

```
updateDraftMessage#1b49ec6d flags:# peer:Peer top_msg_id:flags.0?int draft:DraftMessage = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | Peer | The peer to which the draft is associated |
| top_msg_id | flags.0?int | ID of the forum topic to which the draft is associated |
| draft | DraftMessage | The draft |


## Type
Update

## Related pages
