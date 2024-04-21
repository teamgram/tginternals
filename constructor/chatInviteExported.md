# chatInviteExported
Exported chat invite

```
chatInviteExported#ab4a819 flags:# revoked:flags.0?true permanent:flags.5?true request_needed:flags.6?true link:string admin_id:long date:int start_date:flags.4?int expire_date:flags.1?int usage_limit:flags.2?int usage:flags.3?int requested:flags.7?int title:flags.8?string = ExportedChatInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoked | flags.0?true | Whether this chat invite was revoked |
| permanent | flags.5?true | Whether this chat invite has no expiration |
| request_needed | flags.6?true | Whether users importing this invite link will have to be approved to join the channel or group |
| link | string | Chat invitation link |
| admin_id | long | ID of the admin that created this chat invite |
| date | int | When was this chat invite created |
| start_date | flags.4?int | When was this chat invite last modified |
| expire_date | flags.1?int | When does this chat invite expire |
| usage_limit | flags.2?int | Maximum number of users that can join using this link |
| usage | flags.3?int | How many users joined using this link |
| requested | flags.7?int | Number of users that have already used this link to join |
| title | flags.8?string | Custom description for the invite link, visible only to admins |


## Type
ExportedChatInvite

## Related pages
