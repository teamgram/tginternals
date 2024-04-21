# channelParticipantsMentions
This filter is used when looking for supergroup members to mention.
This filter will automatically remove anonymous admins, and return even non-participant users that replied to a specific thread through the comment section of a channel.

```
channelParticipantsMentions#e04b5ceb flags:# q:flags.0?string top_msg_id:flags.1?int = ChannelParticipantsFilter;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| q | flags.0?string | Filter by user name or username |
| top_msg_id | flags.1?int | Look only for users that posted in this thread |


## Type
ChannelParticipantsFilter

## Related pages
