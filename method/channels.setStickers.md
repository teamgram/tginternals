# channels.setStickers
Associate a stickerset to the supergroup

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.setStickers#ea8ca4f9 channel:InputChannel stickerset:InputStickerSet = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Supergroup |
| stickerset | InputStickerSet | The stickerset to associate |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHAT_ID_INVALID | The provided chat id is invalid. |
| 400 | PARTICIPANTS_TOO_FEW | Not enough participants. |
| 406 | STICKERSET_OWNER_ANONYMOUS | Provided stickerset can't be installed as group stickerset to prevent admin deanonymization. |

