# messages.checkChatInvite
Check the validity of a chat invite link and get basic info about it

```
chatInviteAlready#5a686d7c chat:Chat = ChatInvite;
chatInvite#cde0ec40 flags:# channel:flags.0?true broadcast:flags.1?true public:flags.2?true megagroup:flags.3?true request_needed:flags.6?true verified:flags.7?true scam:flags.8?true fake:flags.9?true title:string about:flags.5?string photo:Photo participants_count:int participants:flags.4?Vector<User> color:int = ChatInvite;
chatInvitePeek#61695cb0 chat:Chat expires:int = ChatInvite;
---functions---
messages.checkChatInvite#3eadb1bb hash:string = ChatInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| hash | string | Invite hash from chat invite deep link ». |


## Result
ChatInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | INVITE_HASH_EMPTY | The invite hash is empty. |
| 406 | INVITE_HASH_EXPIRED | The invite link has expired. |
| 400 | INVITE_HASH_INVALID | The invite hash is invalid. |

