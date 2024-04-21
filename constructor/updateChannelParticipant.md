# updateChannelParticipant
A participant has left, joined, was banned or admined in a channel or supergroup.

```
updateChannelParticipant#985d3abb flags:# via_chatlist:flags.3?true channel_id:long date:int actor_id:long user_id:long prev_participant:flags.0?ChannelParticipant new_participant:flags.1?ChannelParticipant invite:flags.2?ExportedChatInvite qts:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| via_chatlist | flags.3?true | Whether the participant joined using a chat folder deep link ». |
| channel_id | long | Channel ID |
| date | int | Date of the event |
| actor_id | long | User that triggered the change (inviter, admin that kicked the user, or the even the user_id itself) |
| user_id | long | User that was affected by the change |
| prev_participant | flags.0?ChannelParticipant | Previous participant status |
| new_participant | flags.1?ChannelParticipant | New participant status |
| invite | flags.2?ExportedChatInvite | Chat invite used to join the channel/supergroup |
| qts | int | New qts value, see updates » for more info. |


## Type
Update

## Related pages
