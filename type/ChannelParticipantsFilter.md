# ChannelParticipantsFilter
Filter for fetching channel participants

```
channelParticipantsRecent#de3f3c79 = ChannelParticipantsFilter;
channelParticipantsAdmins#b4608969 = ChannelParticipantsFilter;
channelParticipantsKicked#a3b54985 q:string = ChannelParticipantsFilter;
channelParticipantsBots#b0d1865b = ChannelParticipantsFilter;
channelParticipantsBanned#1427a5e1 q:string = ChannelParticipantsFilter;
channelParticipantsSearch#656ac4b q:string = ChannelParticipantsFilter;
channelParticipantsContacts#bb6ae88d q:string = ChannelParticipantsFilter;
channelParticipantsMentions#e04b5ceb flags:# q:flags.0?string top_msg_id:flags.1?int = ChannelParticipantsFilter;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| channelParticipantsRecent | Fetch only recent participants |
| channelParticipantsAdmins | Fetch only admin participants |
| channelParticipantsKicked | Fetch only kicked participants |
| channelParticipantsBots | Fetch only bot participants |
| channelParticipantsBanned | Fetch only banned participants |
| channelParticipantsSearch | Query participants by name |
| channelParticipantsContacts | Fetch only participants that are also contacts |
| channelParticipantsMentions | This filter is used when looking for supergroup members to mention.  This filter will automatically remove anonymous admins, and return even non-participant users that replied to a specific thread through the comment section of a channel. |


## Methods
| Method | Description |
| ---- | ----------- |


