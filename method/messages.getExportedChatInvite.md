# messages.getExportedChatInvite
Get info about a chat invite

```
messages.exportedChatInvite#1871be50 invite:ExportedChatInvite users:Vector<User> = messages.ExportedChatInvite;
messages.exportedChatInviteReplaced#222600ef invite:ExportedChatInvite new_invite:ExportedChatInvite users:Vector<User> = messages.ExportedChatInvite;
---functions---
messages.getExportedChatInvite#73746f5c peer:InputPeer link:string = messages.ExportedChatInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Chat |
| link | string | Invite link |


## Result
messages.ExportedChatInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | INVITE_HASH_EXPIRED | The invite link has expired. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

