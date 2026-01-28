# payments.deleteStarGiftCollection
Delete a star gift collection ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.deleteStarGiftCollection#ad5648e8 peer:InputPeer collection_id:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer that owns the collection. |
| collection_id | int | ID of the collection. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

