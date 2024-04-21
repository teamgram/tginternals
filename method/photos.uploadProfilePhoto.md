# photos.uploadProfilePhoto
Updates current user profile photo.

```
photos.photo#20212ca8 photo:Photo users:Vector<User> = photos.Photo;
---functions---
photos.uploadProfilePhoto#388a3b5 flags:# fallback:flags.3?true bot:flags.5?InputUser file:flags.0?InputFile video:flags.1?InputFile video_start_ts:flags.2?double video_emoji_markup:flags.4?VideoSize = photos.Photo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| fallback | flags.3?true | If set, the chosen profile photo will be shown to users that can't display your main profile photo due to your privacy settings. |
| bot | flags.5?InputUser | Can contain info of a bot we own, to change the profile photo of that bot, instead of the current user. |
| file | flags.0?InputFile | Profile photo |
| video | flags.1?InputFile | Animated profile picture video |
| video_start_ts | flags.2?double | Floating point UNIX timestamp in seconds, indicating the frame of the video/sticker that should be used as static preview; can only be used if video or video_emoji_markup is set. |
| video_emoji_markup | flags.4?VideoSize | Animated sticker profile picture, must contain either a videoSizeEmojiMarkup or a videoSizeStickerMarkup constructor. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ALBUM_PHOTOS_TOO_MANY | You have uploaded too many profile photos, delete some before retrying. |
| 400 | BOT_INVALID | This is not a valid bot. |
| 400 | EMOJI_MARKUP_INVALID | The specified video_emoji_markup was invalid. |
| 400 | FILE_PARTS_INVALID | The number of file parts is invalid. |
| 400 | IMAGE_PROCESS_FAILED | Failure while processing image. |
| 400 | PHOTO_CROP_FILE_MISSING | Photo crop file missing. |
| 400 | PHOTO_CROP_SIZE_SMALL | Photo is too small. |
| 400 | PHOTO_EXT_INVALID | The extension of the photo is invalid. |
| 400 | PHOTO_FILE_MISSING | Profile photo file missing. |
| 400 | PHOTO_INVALID | Photo invalid. |
| 400 | STICKER_MIME_INVALID | The specified sticker MIME type is invalid. |
| 400 | VIDEO_FILE_INVALID | The specified video file is invalid. |

