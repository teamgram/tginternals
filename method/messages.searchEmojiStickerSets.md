# messages.searchEmojiStickerSets
Search for custom emoji stickersets »

```
messages.foundStickerSetsNotModified#d54b65d = messages.FoundStickerSets;
messages.foundStickerSets#8af09dd2 hash:long sets:Vector<StickerSetCovered> = messages.FoundStickerSets;
---functions---
messages.searchEmojiStickerSets#92b4494c flags:# exclude_featured:flags.0?true q:string hash:long = messages.FoundStickerSets;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| exclude_featured | flags.0?true | Exclude featured stickersets from results |
| q | string | Query string |
| hash | long | Hash for pagination, for more info click here |


## Result
messages.FoundStickerSets

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

