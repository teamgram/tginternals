# messageActionTopicCreate
A forum topic was created.

```
messageActionTopicCreate#d999256 flags:# title:string icon_color:int icon_emoji_id:flags.0?long = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| title | string | Topic name. |
| icon_color | int | If no custom emoji icon is specified, specifies the color of the fallback topic icon (RGB), one of 0x6FB9F0, 0xFFD67E, 0xCB86DB, 0x8EEE98, 0xFF93B2, or 0xFB6F5F. |
| icon_emoji_id | flags.0?long | ID of the custom emoji used as topic icon. |


## Type
MessageAction

## Related pages
