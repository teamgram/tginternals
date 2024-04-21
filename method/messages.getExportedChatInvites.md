# messages.getExportedChatInvites
Get info about the chat invites of a specific chat

```
messages.exportedChatInvites#bdc62dcc count:int invites:Vector<ExportedChatInvite> users:Vector<User> = messages.ExportedChatInvites;
---functions---
messages.getExportedChatInvites#a2b5a3f6 flags:# revoked:flags.3?true peer:InputPeer admin_id:InputUser offset_date:flags.2?int offset_link:flags.2?string limit:int = messages.ExportedChatInvites;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| revoked | flags.3?true | Whether to fetch revoked chat invites |
| peer | InputPeer | Chat |
| admin_id | InputUser | Whether to only fetch chat invites from this admin |
| offset_date | flags.2?int | Offsets for pagination, for more info click here |
| offset_link | flags.2?string | Offsets for pagination, for more info click here |
| limit | int | Maximum number of results to return, see pagination |


## Result
messages.ExportedChatInvites

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ADMIN_ID_INVALID | The specified admin ID is invalid. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

