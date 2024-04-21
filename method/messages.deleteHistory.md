# messages.deleteHistory
Deletes communication history.

```
messages.affectedHistory#b45c69d1 pts:int pts_count:int offset:int = messages.AffectedHistory;
---functions---
messages.deleteHistory#b08f922a flags:# just_clear:flags.0?true revoke:flags.1?true peer:InputPeer max_id:int min_date:flags.2?int max_date:flags.3?int = messages.AffectedHistory;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| just_clear | flags.0?true | Just clear history for the current user, without actually removing messages for every chat user |
| revoke | flags.1?true | Whether to delete the message history for all chat participants |
| peer | InputPeer | User or chat, communication history of which will be deleted |
| max_id | int | Maximum ID of message to delete |
| min_date | flags.2?int | Delete all messages newer than this UNIX timestamp |
| max_date | flags.3?int | Delete all messages older than this UNIX timestamp |


## Result
messages.AffectedHistory

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | CHAT_REVOKE_DATE_UNSUPPORTED | min_date and max_date are not available for using with non-user peers. |
| 400 | MAX_DATE_INVALID | The specified maximum date is invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | MIN_DATE_INVALID | The specified minimum date is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

