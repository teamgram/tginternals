# payments.toggleStarGiftsPinnedToTop
Pins a received gift on top of the profile of the user or owned channels by using payments.toggleStarGiftsPinnedToTop.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
payments.toggleStarGiftsPinnedToTop#1513e7b0 peer:InputPeer stargift:Vector<InputSavedStarGift> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer where to pin the gift. |
| stargift | Vector<InputSavedStarGift> | The gift to pin. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

