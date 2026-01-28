# messages.searchStickers
Search for stickers using AI-powered keyword search

```
messages.foundStickersNotModified#6010c534 flags:# next_offset:flags.0?int = messages.FoundStickers;
messages.foundStickers#82c9e290 flags:# next_offset:flags.0?int hash:long stickers:Vector<Document> = messages.FoundStickers;
---functions---
messages.searchStickers#29b1c66a flags:# emojis:flags.0?true q:string emoticon:string lang_code:Vector<string> offset:int limit:int hash:long = messages.FoundStickers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| emojis | flags.0?true | If set, returns custom emoji stickers |
| q | string | The search term |
| emoticon | string | Space-separated list of emojis to search for |
| lang_code | Vector<string> | List of possible IETF language tags of the user's input language; may be empty if unknown |
| offset | int | Offset for pagination |
| limit | int | Maximum number of results to return, see pagination |
| hash | long | Hash used for caching, for more info click here. The hash may be generated locally by using the ids of the returned or stored sticker documents. |


## Result
messages.FoundStickers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

