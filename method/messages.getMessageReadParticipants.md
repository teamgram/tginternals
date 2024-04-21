# messages.getMessageReadParticipants
Get which users read a specific message: only available for groups and supergroups with less than chat_read_mark_size_threshold members, read receipts will be stored for chat_read_mark_expire_period seconds after the message was sent, see client configuration for more info ».

```
---functions---
messages.getMessageReadParticipants#31c1c44f peer:InputPeer msg_id:int = Vector<ReadParticipantDate>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Dialog |
| msg_id | int | Message ID |


## Result
Vector<ReadParticipantDate>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHAT_TOO_BIG | This method is not available for groups with more than chat_read_mark_size_threshold members, see client configuration ». |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | MSG_TOO_OLD | chat_read_mark_expire_period seconds have passed since the message was sent, read receipts were deleted. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

