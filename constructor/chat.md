# chat
Info about a group

```
chat#41cbf256 flags:# creator:flags.0?true left:flags.2?true deactivated:flags.5?true call_active:flags.23?true call_not_empty:flags.24?true noforwards:flags.25?true id:long title:string photo:ChatPhoto participants_count:int date:int version:int migrated_to:flags.6?InputChannel admin_rights:flags.14?ChatAdminRights default_banned_rights:flags.18?ChatBannedRights = Chat;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| creator | flags.0?true | Whether the current user is the creator of the group |
| left | flags.2?true | Whether the current user has left the group |
| deactivated | flags.5?true | Whether the group was migrated |
| call_active | flags.23?true | Whether a group call is currently active |
| call_not_empty | flags.24?true | Whether there's anyone in the group call |
| noforwards | flags.25?true | Whether this group is protected, thus does not allow forwarding messages from it |
| id | long | ID of the group |
| title | string | Title |
| photo | ChatPhoto | Chat photo |
| participants_count | int | Participant count |
| date | int | Date of creation of the group |
| version | int | Used in basic groups to reorder updates and make sure that all of them were received. |
| migrated_to | flags.6?InputChannel | Means this chat was upgraded to a supergroup |
| admin_rights | flags.14?ChatAdminRights | Admin rights of the user in the group |
| default_banned_rights | flags.18?ChatBannedRights | Default banned rights of all users in the group |


## Type
Chat

## Related pages
