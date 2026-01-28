# contacts.resolveUsername
Resolve a @username to get peer info

```
contacts.resolvedPeer#7f077ad9 peer:Peer chats:Vector<Chat> users:Vector<User> = contacts.ResolvedPeer;
---functions---
contacts.resolveUsername#725afbbc flags:# username:string referer:flags.0?string = contacts.ResolvedPeer;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| username | string | @username to resolve |
| referer | flags.0?string | Referrer ID from referral links ». |


## Result
contacts.ResolvedPeer

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CONNECTION_LAYER_INVALID | Layer invalid. |
| 400 | STARREF_EXPIRED | The specified referral link is invalid. |
| 400 | USERNAME_INVALID | The provided username is not valid. |
| 400 | USERNAME_NOT_OCCUPIED | The provided username is not occupied. |

