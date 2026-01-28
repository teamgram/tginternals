# channels.getSendAs
Obtains a list of peers that can be used to send messages in a specific group

```
channels.sendAsPeers#f496b0c6 peers:Vector<SendAsPeer> chats:Vector<Chat> users:Vector<User> = channels.SendAsPeers;
---functions---
channels.getSendAs#e785a43f flags:# for_paid_reactions:flags.0?true peer:InputPeer = channels.SendAsPeers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| for_paid_reactions | flags.0?true | If set, fetches the list of peers that can be used to send paid reactions to messages of a specific peer. |
| peer | InputPeer | The group where we intend to send messages |


## Result
channels.SendAsPeers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

