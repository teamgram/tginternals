# Messages.StickerSet
Stickerset

```
messages.stickerSet#6e153f16 set:StickerSet packs:Vector<StickerPack> keywords:Vector<StickerKeyword> documents:Vector<Document> = messages.StickerSet;
messages.stickerSetNotModified#d3f924eb = messages.StickerSet;

---functions---

messages.getStickerSet#c8a0ec74 stickerset:InputStickerSet hash:int = messages.StickerSet;

stickers.createStickerSet#9021ab67 flags:# masks:flags.0?true animated:flags.1?true videos:flags.4?true emojis:flags.5?true text_color:flags.6?true user_id:InputUser title:string short_name:string thumb:flags.2?InputDocument stickers:Vector<InputStickerSetItem> software:flags.3?string = messages.StickerSet;
stickers.removeStickerFromSet#f7760f51 sticker:InputDocument = messages.StickerSet;
stickers.changeStickerPosition#ffb6d4ca sticker:InputDocument position:int = messages.StickerSet;
stickers.addStickerToSet#8653febe stickerset:InputStickerSet sticker:InputStickerSetItem = messages.StickerSet;
stickers.setStickerSetThumb#a76a5392 flags:# stickerset:InputStickerSet thumb:flags.0?InputDocument thumb_document_id:flags.1?long = messages.StickerSet;
stickers.changeSticker#f5537ebc flags:# sticker:InputDocument emoji:flags.0?string mask_coords:flags.1?MaskCoords keywords:flags.2?string = messages.StickerSet;
stickers.renameStickerSet#124b1c00 stickerset:InputStickerSet title:string = messages.StickerSet;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.stickerSet | Stickerset and stickers inside it |
| messages.stickerSetNotModified | The stickerset hasn't changed |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getStickerSet | Get info about a stickerset |
| stickers.createStickerSet | Create a stickerset, bots only. |
| stickers.removeStickerFromSet | Remove a sticker from the set where it belongs, bots only. The sticker set must have been created by the bot. |
| stickers.changeStickerPosition | Changes the absolute position of a sticker in the set to which it belongs; for bots only. The sticker set must have been created by the bot |
| stickers.addStickerToSet | Add a sticker to a stickerset, bots only. The sticker set must have been created by the bot. |
| stickers.setStickerSetThumb | Set stickerset thumbnail |
| stickers.changeSticker | Update the keywords, emojis or mask coordinates of a sticker, bots only. |
| stickers.renameStickerSet | Renames a stickerset, bots only. |


