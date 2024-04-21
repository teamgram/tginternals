# messages.reorderStickerSets
Reorder installed stickersets

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.reorderStickerSets#78337739 flags:# masks:flags.0?true emojis:flags.1?true order:Vector<long> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| masks | flags.0?true | Reorder mask stickersets |
| emojis | flags.1?true | Reorder custom emoji stickersets |
| order | Vector<long> | New stickerset order by stickerset IDs |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

