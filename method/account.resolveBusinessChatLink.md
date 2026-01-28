# account.resolveBusinessChatLink
Resolve a business chat deep link ».

```
account.resolvedBusinessChatLinks#9a23af21 flags:# peer:Peer message:string entities:flags.0?Vector<MessageEntity> chats:Vector<Chat> users:Vector<User> = account.ResolvedBusinessChatLinks;
---functions---
account.resolveBusinessChatLink#5492e5ee slug:string = account.ResolvedBusinessChatLinks;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| slug | string | Slug of the link, obtained as specified here ». |


## Result
account.ResolvedBusinessChatLinks

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHATLINK_SLUG_EMPTY | The specified slug is empty. |
| 400 | CHATLINK_SLUG_EXPIRED | The specified business chat link has expired. |

