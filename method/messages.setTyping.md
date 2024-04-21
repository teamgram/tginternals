# messages.setTyping
Sends a current user typing event (see SendMessageAction for all event types) to a conversation partner or group.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setTyping#58943ee2 flags:# peer:InputPeer top_msg_id:flags.0?int action:SendMessageAction = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Target user or group |
| top_msg_id | flags.0?int | Topic ID |
| action | SendMessageAction | Type of action |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 403 | GROUPCALL_FORBIDDEN | The group call has already ended. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USER_BANNED_IN_CHANNEL | You're banned from sending messages in supergroups/channels. |
| 403 | USER_IS_BLOCKED | You were blocked by this user. |
| 400 | USER_IS_BOT | Bots can't send messages to other bots. |

