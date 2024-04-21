# messages.getOnlines
Get count of online users in a chat

```
chatOnlines#f041e250 onlines:int = ChatOnlines;
---functions---
messages.getOnlines#6e2be050 peer:InputPeer = ChatOnlines;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The chat |


## Result
ChatOnlines

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

