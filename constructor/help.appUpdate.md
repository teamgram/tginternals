# help.appUpdate
An update is available for the application.

```
help.appUpdate#ccbbce30 flags:# can_not_skip:flags.0?true id:int version:string text:string entities:Vector<MessageEntity> document:flags.1?Document url:flags.2?string sticker:flags.3?Document = help.AppUpdate;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| can_not_skip | flags.0?true | Unskippable, the new info must be shown to the user (with a popup or something else) |
| id | int | Update ID |
| version | string | New version name |
| text | string | Text description of the update |
| entities | Vector<MessageEntity> | Message entities for styled text |
| document | flags.1?Document | Application binary |
| url | flags.2?string | Application download URL |
| sticker | flags.3?Document | Associated sticker |


## Type
help.AppUpdate

## Related pages
