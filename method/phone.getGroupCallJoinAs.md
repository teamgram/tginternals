# phone.getGroupCallJoinAs
Get a list of peers that can be used to join a group call, presenting yourself as a specific user/channel.

```
phone.joinAsPeers#afe5623f peers:Vector<Peer> chats:Vector<Chat> users:Vector<User> = phone.JoinAsPeers;
---functions---
phone.getGroupCallJoinAs#ef7c213a peer:InputPeer = phone.JoinAsPeers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The dialog whose group call or livestream we're trying to join |


## Result
phone.JoinAsPeers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

