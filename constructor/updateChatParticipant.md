# updateChatParticipant
A user has joined or left a specific chat

```
updateChatParticipant#d087663a flags:# chat_id:long date:int actor_id:long user_id:long prev_participant:flags.0?ChatParticipant new_participant:flags.1?ChatParticipant invite:flags.2?ExportedChatInvite qts:int = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| chat_id | long | Chat ID |
| date | int | When did this event occur |
| actor_id | long | User that triggered the change (inviter, admin that kicked the user, or the even the user_id itself) |
| user_id | long | User that was affected by the change |
| prev_participant | flags.0?ChatParticipant | Previous participant info (empty if this participant just joined) |
| new_participant | flags.1?ChatParticipant | New participant info (empty if this participant just left) |
| invite | flags.2?ExportedChatInvite | The invite that was used to join the group |
| qts | int | New qts value, see updates » for more info. |


## Type
Update

## Related pages
