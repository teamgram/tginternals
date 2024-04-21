# channelParticipantAdmin
Admin

```
channelParticipantAdmin#34c3bb53 flags:# can_edit:flags.0?true self:flags.1?true user_id:long inviter_id:flags.1?long promoted_by:long date:int admin_rights:ChatAdminRights rank:flags.2?string = ChannelParticipant;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| can_edit | flags.0?true | Can this admin promote other admins with the same permissions? |
| self | flags.1?true | Is this the current user |
| user_id | long | Admin user ID |
| inviter_id | flags.1?long | User that invited the admin to the channel/group |
| promoted_by | long | User that promoted the user to admin |
| date | int | When did the user join |
| admin_rights | ChatAdminRights | Admin rights |
| rank | flags.2?string | The role (rank) of the admin in the group: just an arbitrary string, admin by default |


## Type
ChannelParticipant

## Related pages
