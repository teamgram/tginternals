# contacts.resolvePhone
Resolve a phone number to get user info, if their privacy settings allow it.

```
contacts.resolvedPeer#7f077ad9 peer:Peer chats:Vector<Chat> users:Vector<User> = contacts.ResolvedPeer;
---functions---
contacts.resolvePhone#8af94344 phone:string = contacts.ResolvedPeer;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone | string | Phone number in international format, possibly obtained from a phone number deep link. |


## Result
contacts.ResolvedPeer

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_NOT_OCCUPIED | No user is associated to the specified phone number. |

