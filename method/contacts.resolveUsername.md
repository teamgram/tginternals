# contacts.resolveUsername
Resolve a @username to get peer info

```
contacts.resolvedPeer#7f077ad9 peer:Peer chats:Vector<Chat> users:Vector<User> = contacts.ResolvedPeer;
---functions---
contacts.resolveUsername#f93ccba3 username:string = contacts.ResolvedPeer;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| username | string | @username to resolve |


## Result
contacts.ResolvedPeer

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CONNECTION_LAYER_INVALID | Layer invalid. |
| 400 | USERNAME_INVALID | The provided username is not valid. |
| 400 | USERNAME_NOT_OCCUPIED | The provided username is not occupied. |

