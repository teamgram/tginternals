# updateChannelReadMessagesContents
The specified channel/supergroup messages were read (emitted specifically for messages like voice messages or video, only once the media is watched and marked as read using channels.readMessageContents)

```
updateChannelReadMessagesContents#25f324f7 flags:# channel_id:long top_msg_id:flags.0?int saved_peer_id:flags.1?Peer messages:Vector<int> = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel_id | long | Channel/supergroup ID |
| top_msg_id | flags.0?int | Forum topic ID. |
| saved_peer_id | flags.1?Peer | If set, the messages were read within the specified monoforum topic ». |
| messages | Vector<int> | IDs of messages that were read |


## Type
Update

## Related pages
