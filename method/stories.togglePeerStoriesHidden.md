# stories.togglePeerStoriesHidden
Hide the active stories of a user, preventing them from being displayed on the action bar on the homescreen, see here » for more info.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
stories.togglePeerStoriesHidden#bd0415c4 peer:InputPeer hidden:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer whose stories should be (un)hidden. |
| hidden | Bool | Whether to hide or unhide stories. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

