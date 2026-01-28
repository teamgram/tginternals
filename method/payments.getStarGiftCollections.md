# payments.getStarGiftCollections
Fetches all star gift collections » of a peer.

```
payments.starGiftCollectionsNotModified#a0ba4f17 = payments.StarGiftCollections;
payments.starGiftCollections#8a2932f3 collections:Vector<StarGiftCollection> = payments.StarGiftCollections;
---functions---
payments.getStarGiftCollections#981b91dd peer:InputPeer hash:long = payments.StarGiftCollections;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer. |
| hash | long | Hash (generated as specified here ») using the starGiftCollection.hash field (not the collection_id field) of all collections returned by a previous method call, to avoid refetching the result if it hasn't changed. |


## Result
payments.StarGiftCollections

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

