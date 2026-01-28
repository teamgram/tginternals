# updateDialogUnreadMark
The manual unread mark of a chat was changed

```
updateDialogUnreadMark#b658f23e flags:# unread:flags.0?true peer:DialogPeer saved_peer_id:flags.1?Peer = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| unread | flags.0?true | Was the chat marked or unmarked as read |
| peer | DialogPeer | The dialog |
| saved_peer_id | flags.1?Peer | If set, the mark is related to the specified monoforum topic ID ». |


## Type
Update

## Related pages
