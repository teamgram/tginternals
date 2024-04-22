# ChannelParticipant
Channel participant

```
channelParticipant#c00c07c0 user_id:long date:int = ChannelParticipant;
channelParticipantSelf#35a8bfa7 flags:# via_request:flags.0?true user_id:long inviter_id:long date:int = ChannelParticipant;
channelParticipantCreator#2fe601d3 flags:# user_id:long admin_rights:ChatAdminRights rank:flags.0?string = ChannelParticipant;
channelParticipantAdmin#34c3bb53 flags:# can_edit:flags.0?true self:flags.1?true user_id:long inviter_id:flags.1?long promoted_by:long date:int admin_rights:ChatAdminRights rank:flags.2?string = ChannelParticipant;
channelParticipantBanned#6df8014e flags:# left:flags.0?true peer:Peer kicked_by:long date:int banned_rights:ChatBannedRights = ChannelParticipant;
channelParticipantLeft#1b03f006 peer:Peer = ChannelParticipant;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| channelParticipant | Channel/supergroup participant |
| channelParticipantSelf | Myself |
| channelParticipantCreator | Channel/supergroup creator |
| channelParticipantAdmin | Admin |
| channelParticipantBanned | Banned/kicked user |
| channelParticipantLeft | A participant that left the channel/supergroup |


## Methods
| Method | Description |
| ---- | ----------- |


