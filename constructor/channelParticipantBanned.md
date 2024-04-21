# channelParticipantBanned
Banned/kicked user

```
channelParticipantBanned#6df8014e flags:# left:flags.0?true peer:Peer kicked_by:long date:int banned_rights:ChatBannedRights = ChannelParticipant;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| left | flags.0?true | Whether the user has left the group |
| peer | Peer | The banned peer |
| kicked_by | long | User was kicked by the specified admin |
| date | int | When did the user join the group |
| banned_rights | ChatBannedRights | Banned rights |


## Type
ChannelParticipant

## Related pages
