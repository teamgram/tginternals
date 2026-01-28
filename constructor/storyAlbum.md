# storyAlbum
Represents a story album ».

```
storyAlbum#9325705a flags:# album_id:int title:string icon_photo:flags.0?Photo icon_video:flags.1?Document = StoryAlbum;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| album_id | int | ID of the album. |
| title | string | Name of the album. |
| icon_photo | flags.0?Photo | Photo from the first story of the album, if it's a photo. |
| icon_video | flags.1?Document | Video from the first story of the album, if it's a video. |


## Type
StoryAlbum

## Related pages
