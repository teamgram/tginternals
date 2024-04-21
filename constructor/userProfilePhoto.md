# userProfilePhoto
User profile photo.

```
userProfilePhoto#82d1f706 flags:# has_video:flags.0?true personal:flags.2?true photo_id:long stripped_thumb:flags.1?bytes dc_id:int = UserProfilePhoto;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_video | flags.0?true | Whether an animated profile picture is available for this user |
| personal | flags.2?true | Whether this profile photo is only visible to us (i.e. it was set using photos.uploadContactProfilePhoto). |
| photo_id | long | Identifier of the respective photo |
| stripped_thumb | flags.1?bytes | Stripped thumbnail |
| dc_id | int | DC ID where the photo is stored |


## Type
UserProfilePhoto

## Related pages
