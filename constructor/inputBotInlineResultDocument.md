# inputBotInlineResultDocument
Document (media of any type except for photos)

```
inputBotInlineResultDocument#fff8fdc4 flags:# id:string type:string title:flags.1?string description:flags.2?string document:InputDocument send_message:InputBotInlineMessage = InputBotInlineResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| id | string | Result ID |
| type | string | Result type (see bot API docs) |
| title | flags.1?string | Result title |
| description | flags.2?string | Result description |
| document | InputDocument | Document to send |
| send_message | InputBotInlineMessage | Message to send when the result is selected |


## Type
InputBotInlineResult

## Related pages
