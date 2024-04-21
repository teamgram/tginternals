# messages.botCallbackAnswer
Callback answer sent by the bot in response to a button press

```
messages.botCallbackAnswer#36585ea4 flags:# alert:flags.1?true has_url:flags.3?true native_ui:flags.4?true message:flags.0?string url:flags.2?string cache_time:int = messages.BotCallbackAnswer;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| alert | flags.1?true | Whether an alert should be shown to the user instead of a toast notification |
| has_url | flags.3?true | Whether an URL is present |
| native_ui | flags.4?true | Whether to show games in WebView or in native UI. |
| message | flags.0?string | Alert to show |
| url | flags.2?string | URL to open |
| cache_time | int | For how long should this answer be cached |


## Type
messages.BotCallbackAnswer

## Related pages
