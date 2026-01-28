# messages.unpinAllMessages
Unpin all pinned messages

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
---functions---
messages.unpinAllMessages#62dd747 flags:# peer:InputPeer top_msg_id:flags.0?int saved_peer_id:flags.1?InputPeer = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Chat where to unpin |
| top_msg_id | flags.0?int | Forum topic where to unpin |
| saved_peer_id | flags.1?InputPeer | If set, must be equal to the ID of a monoforum topic, and will unpin all messages pinned in the passed monoforum topic. |


## Result
messages.AffectedHistory

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_NOT_MODIFIED | No changes were made to chat information because the new information you passed is identical to the current information. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

