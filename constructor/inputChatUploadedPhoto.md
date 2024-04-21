# inputChatUploadedPhoto
New photo to be set as group profile photo.

```
inputChatUploadedPhoto#bdcdaec0 flags:# file:flags.0?InputFile video:flags.1?InputFile video_start_ts:flags.2?double video_emoji_markup:flags.3?VideoSize = InputChatPhoto;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| file | flags.0?InputFile | File saved in parts using the method upload.saveFilePart |
| video | flags.1?InputFile | Square video for animated profile picture |
| video_start_ts | flags.2?double | Floating point UNIX timestamp in seconds, indicating the frame of the video/sticker that should be used as static preview; can only be used if video or video_emoji_markup is set. |
| video_emoji_markup | flags.3?VideoSize | Animated sticker profile picture, must contain either a videoSizeEmojiMarkup or a videoSizeStickerMarkup constructor. |


## Type


## Related pages
