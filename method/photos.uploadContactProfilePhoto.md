# photos.uploadContactProfilePhoto
Upload a custom profile picture for a contact, or suggest a new profile picture to a contact.

```
photos.photo#20212ca8 photo:Photo users:Vector<User> = photos.Photo;
---functions---
photos.uploadContactProfilePhoto#e14c4a71 flags:# suggest:flags.3?true save:flags.4?true user_id:InputUser file:flags.0?InputFile video:flags.1?InputFile video_start_ts:flags.2?double video_emoji_markup:flags.5?VideoSize = photos.Photo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| suggest | flags.3?true | If set, will send a messageActionSuggestProfilePhoto service message to user_id, suggesting them to use the specified profile picture; otherwise, will set a personal profile picture for the user (only visible to the current user). |
| save | flags.4?true | If set, removes a previously set personal profile picture (does not affect suggested profile pictures, to remove them simply deleted the messageActionSuggestProfilePhoto service message with messages.deleteMessages). |
| user_id | InputUser | The contact |
| file | flags.0?InputFile | Profile photo |
| video | flags.1?InputFile | Animated profile picture video |
| video_start_ts | flags.2?double | Floating point UNIX timestamp in seconds, indicating the frame of the video/sticker that should be used as static preview; can only be used if video or video_emoji_markup is set. |
| video_emoji_markup | flags.5?VideoSize | Animated sticker profile picture, must contain either a videoSizeEmojiMarkup or a videoSizeStickerMarkup constructor. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CONTACT_MISSING | The specified user is not a contact. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

