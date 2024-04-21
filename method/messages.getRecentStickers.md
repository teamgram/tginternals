# messages.getRecentStickers
Get recent stickers

```
messages.recentStickersNotModified#b17f890 = messages.RecentStickers;
messages.recentStickers#88d37c56 hash:long packs:Vector<StickerPack> stickers:Vector<Document> dates:Vector<int> = messages.RecentStickers;
---functions---
messages.getRecentStickers#9da9403b flags:# attached:flags.0?true hash:long = messages.RecentStickers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| attached | flags.0?true | Get stickers recently attached to photo or video files |
| hash | long | Hash for pagination, for more info click here |


## Result
messages.RecentStickers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

