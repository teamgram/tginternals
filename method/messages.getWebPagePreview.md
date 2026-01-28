# messages.getWebPagePreview
Get preview of webpage

```
messages.webPagePreview#8c9a88ac media:MessageMedia chats:Vector<Chat> users:Vector<User> = messages.WebPagePreview;
---functions---
messages.getWebPagePreview#570d6f6f flags:# message:string entities:flags.3?Vector<MessageEntity> = messages.WebPagePreview;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| message | string | Message from which to extract the preview |
| entities | flags.3?Vector<MessageEntity> | Message entities for styled text |


## Result
messages.WebPagePreview

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 400 | MESSAGE_EMPTY | The provided message is empty. |

