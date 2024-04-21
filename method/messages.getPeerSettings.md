# messages.getPeerSettings
Get peer settings

```
messages.peerSettings#6880b94d settings:PeerSettings chats:Vector<Chat> users:Vector<User> = messages.PeerSettings;
---functions---
messages.getPeerSettings#efd9a6a2 peer:InputPeer = messages.PeerSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer |


## Result
messages.PeerSettings

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

