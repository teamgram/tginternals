# botInlineMediaResult
Media result

```
botInlineMediaResult#17db940b flags:# id:string type:string photo:flags.0?Photo document:flags.1?Document title:flags.2?string description:flags.3?string send_message:BotInlineMessage = BotInlineResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| id | string | Result ID |
| type | string | Result type (see bot API docs) |
| photo | flags.0?Photo | If type is photo, the photo to send |
| document | flags.1?Document | If type is document, the document to send |
| title | flags.2?string | Result title |
| description | flags.3?string | Description |
| send_message | BotInlineMessage | Depending on the type and on the constructor, contains the caption of the media or the content of the message to be sent instead of the media |


## Type
BotInlineResult

## Related pages
