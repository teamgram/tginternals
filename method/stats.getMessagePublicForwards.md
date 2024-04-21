# stats.getMessagePublicForwards
Obtains a list of messages, indicating to which other public channels was a channel message forwarded.
Will return a list of messages with peer_id equal to the public channel to which this message was forwarded.

```
stats.publicForwards#93037e20 flags:# count:int forwards:Vector<PublicForward> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stats.PublicForwards;
---functions---
stats.getMessagePublicForwards#5f150144 channel:InputChannel msg_id:int offset:string limit:int = stats.PublicForwards;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Source channel |
| msg_id | int | Source message ID |
| offset | string | Offset for pagination, empty string on first call, then use the next_offset field of the returned constructor (if present, otherwise no more results are available). |
| limit | int | Maximum number of results to return, see pagination |


## Result
stats.PublicForwards

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

