# messages.getArchivedStickers
Get all archived stickers

```
messages.archivedStickers#4fcba9c8 count:int sets:Vector<StickerSetCovered> = messages.ArchivedStickers;
---functions---
messages.getArchivedStickers#57f17692 flags:# masks:flags.0?true emojis:flags.1?true offset_id:long limit:int = messages.ArchivedStickers;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| masks | flags.0?true | Get mask stickers |
| emojis | flags.1?true | Get custom emoji stickers |
| offset_id | long | Offsets for pagination, for more info click here |
| limit | int | Maximum number of results to return, see pagination |


## Result
messages.ArchivedStickers

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

