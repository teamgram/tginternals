# stats.getStoryPublicForwards
Obtain forwards of a story as a message to public chats and reposts by public channels.

```
stats.publicForwards#93037e20 flags:# count:int forwards:Vector<PublicForward> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stats.PublicForwards;
---functions---
stats.getStoryPublicForwards#a6437ef6 peer:InputPeer id:int offset:string limit:int = stats.PublicForwards;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where the story was originally posted |
| id | int | Story ID |
| offset | string | Offset for pagination, from stats.PublicForwards.next_offset. |
| limit | int | Maximum number of results to return, see pagination |


## Result
stats.PublicForwards

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

