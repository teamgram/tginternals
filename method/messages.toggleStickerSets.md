# messages.toggleStickerSets
Apply changes to multiple stickersets

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.toggleStickerSets#b5052fea flags:# uninstall:flags.0?true archive:flags.1?true unarchive:flags.2?true stickersets:Vector<InputStickerSet> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| uninstall | flags.0?true | Uninstall the specified stickersets |
| archive | flags.1?true | Archive the specified stickersets |
| unarchive | flags.2?true | Unarchive the specified stickersets |
| stickersets | Vector<InputStickerSet> | Stickersets to act upon |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

