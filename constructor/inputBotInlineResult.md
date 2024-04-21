# inputBotInlineResult
An inline bot result

```
inputBotInlineResult#88bf9319 flags:# id:string type:string title:flags.1?string description:flags.2?string url:flags.3?string thumb:flags.4?InputWebDocument content:flags.5?InputWebDocument send_message:InputBotInlineMessage = InputBotInlineResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| id | string | ID of result |
| type | string | Result type (see bot API docs) |
| title | flags.1?string | Result title |
| description | flags.2?string | Result description |
| url | flags.3?string | URL of result |
| thumb | flags.4?InputWebDocument | Thumbnail for result |
| content | flags.5?InputWebDocument | Result contents |
| send_message | InputBotInlineMessage | Message to send when the result is selected |


## Type
InputBotInlineResult

## Related pages
