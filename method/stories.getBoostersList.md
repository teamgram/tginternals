# stories.getBoostersList
Obtain info about the users currently boosting a channel, see here » for more info about boosts.

```
Method schema is available as of layer 166. Switch »
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The channel. |
| offset | string | Next offset for pagination, obtained from the next_offset field of stories.boostersList. |
| limit | int | Maximum number of results to return, see pagination |


## Result
 

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

