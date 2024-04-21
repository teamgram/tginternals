# messages.installStickerSet
Install a stickerset

```
messages.stickerSetInstallResultSuccess#38641628 = messages.StickerSetInstallResult;
messages.stickerSetInstallResultArchive#35e410a8 sets:Vector<StickerSetCovered> = messages.StickerSetInstallResult;
---functions---
messages.installStickerSet#c78fe460 stickerset:InputStickerSet archived:Bool = messages.StickerSetInstallResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| stickerset | InputStickerSet | Stickerset to install |
| archived | Bool | Whether to archive stickerset |


## Result
messages.StickerSetInstallResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 406 | STICKERSET_INVALID | The provided sticker set is invalid. |

