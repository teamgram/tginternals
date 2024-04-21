# messages.getOldFeaturedStickers
Method for fetching previously featured stickers

```
messages.featuredStickersNotModified#c6dc0c66 count:int = messages.FeaturedStickers;
messages.featuredStickers#be382906 flags:# premium:flags.0?true hash:long count:int sets:Vector<StickerSetCovered> unread:Vector<long> = messages.FeaturedStickers;
---functions---
messages.getOldFeaturedStickers#7ed094a1 offset:int limit:int hash:long = messages.FeaturedStickers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| offset | int | Offset |
| limit | int | Maximum number of results to return, see pagination |
| hash | long | Hash for pagination, for more info click here |


## Result
messages.FeaturedStickers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

