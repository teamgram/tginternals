# contacts.resetTopPeerRating
Reset rating of top peer

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
contacts.resetTopPeerRating#1ae373ac category:TopPeerCategory peer:InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| category | TopPeerCategory | Top peer category |
| peer | InputPeer | Peer whose rating should be reset |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

