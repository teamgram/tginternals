# chatlists.checkChatlistInvite
Obtain information about a chat folder deep link ».

```
chatlists.chatlistInviteAlready#fa87f659 filter_id:int missing_peers:Vector<Peer> already_peers:Vector<Peer> chats:Vector<Chat> users:Vector<User> = chatlists.ChatlistInvite;
chatlists.chatlistInvite#1dcd839d flags:# title:string emoticon:flags.0?string peers:Vector<Peer> chats:Vector<Chat> users:Vector<User> = chatlists.ChatlistInvite;
---functions---
chatlists.checkChatlistInvite#41c10fff slug:string = chatlists.ChatlistInvite;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| slug | string | slug obtained from the chat folder deep link » |


## Result
chatlists.ChatlistInvite

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | INVITE_SLUG_EMPTY | The specified invite slug is empty. |
| 400 | INVITE_SLUG_EXPIRED | The specified chat folder link has expired. |

