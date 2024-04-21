# DocumentAttribute
Various possible attributes of a document (used to define if it's a sticker, a GIF, a video, a mask sticker, an image, an audio, and so on)

```
documentAttributeImageSize#6c37c15c w:int h:int = DocumentAttribute;
documentAttributeAnimated#11b58939 = DocumentAttribute;
documentAttributeSticker#6319d612 flags:# mask:flags.1?true alt:string stickerset:InputStickerSet mask_coords:flags.0?MaskCoords = DocumentAttribute;
documentAttributeVideo#d38ff1c2 flags:# round_message:flags.0?true supports_streaming:flags.1?true nosound:flags.3?true duration:double w:int h:int preload_prefix_size:flags.2?int = DocumentAttribute;
documentAttributeAudio#9852f9c6 flags:# voice:flags.10?true duration:int title:flags.0?string performer:flags.1?string waveform:flags.2?bytes = DocumentAttribute;
documentAttributeFilename#15590068 file_name:string = DocumentAttribute;
documentAttributeHasStickers#9801d2f7 = DocumentAttribute;
documentAttributeCustomEmoji#fd149899 flags:# free:flags.0?true text_color:flags.1?true alt:string stickerset:InputStickerSet = DocumentAttribute;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| documentAttributeImageSize | Defines the width and height of an image uploaded as document |
| documentAttributeAnimated | Defines an animated GIF |
| documentAttributeSticker | Defines a sticker |
| documentAttributeVideo | Defines a video |
| documentAttributeAudio | Represents an audio file |
| documentAttributeFilename | A simple document with a file name |
| documentAttributeHasStickers | Whether the current document has stickers attached |
| documentAttributeCustomEmoji | Info about a custom emoji |


## Methods
| Method | Description |
| ---- | ----------- |


