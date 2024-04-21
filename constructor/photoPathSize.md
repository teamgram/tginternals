# photoPathSize
Messages with animated stickers can have a compressed svg (< 300 bytes) to show the outline of the sticker before fetching the actual lottie animation.

```
photoPathSize#d8214d41 type:string bytes:bytes = PhotoSize;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| type | string | Always j |
| bytes | bytes | Compressed SVG path payload, see here for decompression instructions |


## Type
PhotoSize

## Related pages
