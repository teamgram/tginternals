# messages.getChatInviteImporters
Get info about the users that joined the chat using a specific chat invite

```
messages.chatInviteImporters#81b6b00a count:int importers:Vector<ChatInviteImporter> users:Vector<User> = messages.ChatInviteImporters;
---functions---
messages.getChatInviteImporters#df04dd4e flags:# requested:flags.0?true peer:InputPeer link:flags.1?string q:flags.2?string offset_date:int offset_user:InputUser limit:int = messages.ChatInviteImporters;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| requested | flags.0?true | If set, only returns info about users with pending join requests » |
| peer | InputPeer | Chat |
| link | flags.1?string | Invite link |
| q | flags.2?string | Search for a user in the pending join requests » list: only available when the requested flag is set, cannot be used together with a specific link. |
| offset_date | int | Offsets for pagination, for more info click here |
| offset_user | InputUser | User ID for pagination: if set, offset_date must also be set. |
| limit | int | Maximum number of results to return, see pagination |


## Result
messages.ChatInviteImporters

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | INVITE_HASH_EXPIRED | The invite link has expired. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | SEARCH_WITH_LINK_NOT_SUPPORTED | You cannot provide a search query and an invite link at the same time. |

