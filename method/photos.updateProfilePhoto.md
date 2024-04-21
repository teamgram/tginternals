# photos.updateProfilePhoto
Installs a previously uploaded photo as a profile photo.

```
photos.photo#20212ca8 photo:Photo users:Vector<User> = photos.Photo;
---functions---
photos.updateProfilePhoto#9e82039 flags:# fallback:flags.0?true bot:flags.1?InputUser id:InputPhoto = photos.Photo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| fallback | flags.0?true | If set, the chosen profile photo will be shown to users that can't display your main profile photo due to your privacy settings. |
| bot | flags.1?InputUser | Can contain info of a bot we own, to change the profile photo of that bot, instead of the current user. |
| id | InputPhoto | Input photo |


## Result
photos.Photo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ALBUM_PHOTOS_TOO_MANY | You have uploaded too many profile photos, delete some before retrying. |
| 400 | FILE_PARTS_INVALID | The number of file parts is invalid. |
| 400 | IMAGE_PROCESS_FAILED | Failure while processing image. |
| 400 | LOCATION_INVALID | The provided location is invalid. |
| 400 | PHOTO_CROP_SIZE_SMALL | Photo is too small. |
| 400 | PHOTO_EXT_INVALID | The extension of the photo is invalid. |
| 400 | PHOTO_ID_INVALID | Photo ID invalid. |

