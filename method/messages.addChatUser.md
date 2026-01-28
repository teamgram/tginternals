# messages.addChatUser
Adds a user to a chat and sends a service message on it.

```
messages.invitedUsers#7f5defa6 updates:Updates missing_invitees:Vector<MissingInvitee> = messages.InvitedUsers;
---functions---
messages.addChatUser#cbc6d107 chat_id:long user_id:InputUser fwd_limit:int = messages.InvitedUsers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| chat_id | long | Chat ID |
| user_id | InputUser | User ID to be added |
| fwd_limit | int | Number of last messages to be forwarded |


## Result
messages.InvitedUsers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_GROUPS_BLOCKED | This bot can't be added to groups. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | CHAT_INVALID | Invalid chat. |
| 400 | CHAT_MEMBER_ADD_FAILED | Could not add participants. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USERS_TOO_MUCH | The maximum number of users has been exceeded (to create a chat, for example). |
| 400 | USER_ALREADY_PARTICIPANT | The user is already in the group. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 400 | USER_IS_BLOCKED | You were blocked by this user. |
| 403 | USER_NOT_MUTUAL_CONTACT | The provided user is not a mutual contact. |
| 403 | USER_PRIVACY_RESTRICTED | The user's privacy settings do not allow you to do this. |
| 400 | YOU_BLOCKED_USER | You blocked this user. |

