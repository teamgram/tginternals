# messages.editExportedChatInvite
Edit an exported chat invite

```
messages.exportedChatInvite#1871be50 invite:ExportedChatInvite users:Vector<User> = messages.ExportedChatInvite;
messages.exportedChatInviteReplaced#222600ef invite:ExportedChatInvite new_invite:ExportedChatInvite users:Vector<User> = messages.ExportedChatInvite;
---functions---
messages.editExportedChatInvite#bdca2f75 flags:# revoked:flags.2?true peer:InputPeer link:string expire_date:flags.0?int usage_limit:flags.1?int request_needed:flags.3?Bool title:flags.4?string = messages.ExportedChatInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoked | flags.2?true | Whether to revoke the chat invite |
| peer | InputPeer | Chat |
| link | string | Invite link |
| expire_date | flags.0?int | New expiration date |
| usage_limit | flags.1?int | Maximum number of users that can join using this link |
| request_needed | flags.3?Bool | Whether admin confirmation is required before admitting each separate user into the chat |
| title | flags.4?string | Description of the invite link, visible only to administrators |


## Result
messages.ExportedChatInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_INVITE_PERMANENT | You can't set an expiration date on permanent invite links. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 403 | EDIT_BOT_INVITE_FORBIDDEN | Normal users can't edit invites that were created by bots. |
| 400 | INVITE_HASH_EXPIRED | The invite link has expired. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USAGE_LIMIT_INVALID | The specified usage limit is invalid. |

