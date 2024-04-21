# Messages.StickerSetInstallResult
Result of stickerset installation process

```
messages.stickerSetInstallResultSuccess#38641628 = messages.StickerSetInstallResult;
messages.stickerSetInstallResultArchive#35e410a8 sets:Vector<StickerSetCovered> = messages.StickerSetInstallResult;

---functions---

messages.installStickerSet#c78fe460 stickerset:InputStickerSet archived:Bool = messages.StickerSetInstallResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.stickerSetInstallResultSuccess | The stickerset was installed successfully |
| messages.stickerSetInstallResultArchive | The stickerset was installed, but since there are too many stickersets some were archived |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.installStickerSet | Install a stickerset |


