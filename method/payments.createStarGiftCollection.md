# payments.createStarGiftCollection
Create a star gift collection ».

```
starGiftCollection#9d6b13b0 flags:# collection_id:int title:string icon:flags.0?Document gifts_count:int hash:long = StarGiftCollection;
---functions---
payments.createStarGiftCollection#1f4a0e87 peer:InputPeer title:string stargift:Vector<InputSavedStarGift> = StarGiftCollection;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Peer where to create the collection. |
| title | string | Title of the collection. |
| stargift | Vector<InputSavedStarGift> | Gifts added to the collection. |


## Result
StarGiftCollection

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

