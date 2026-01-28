# messages.createChat
Creates a new chat.

```
messages.invitedUsers#7f5defa6 updates:Updates missing_invitees:Vector<MissingInvitee> = messages.InvitedUsers;
---functions---
messages.createChat#92ceddd4 flags:# users:Vector<InputUser> title:string ttl_period:flags.0?int = messages.InvitedUsers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| users | Vector<InputUser> | List of user IDs to be invited |
| title | string | Chat name |
| ttl_period | flags.0?int | Time-to-live of all messages that will be sent in the chat: once message.date+message.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. You can use messages.setDefaultHistoryTTL to edit this value later. |


## Result
messages.InvitedUsers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 500 | CHAT_ID_GENERATE_FAILED | Failure while generating the chat ID. |
| 400 | CHAT_INVALID | Invalid chat. |
| 400 | CHAT_MEMBER_ADD_FAILED | Could not add participants. |
| 400 | CHAT_TITLE_EMPTY | No chat title provided. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | TTL_PERIOD_INVALID | The specified TTL period is invalid. |
| 400 | USERS_TOO_FEW | Not enough users (to create a chat, for example). |
| 403 | USER_RESTRICTED | You're spamreported, you can't create channels or chats. |

