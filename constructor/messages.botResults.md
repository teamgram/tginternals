# messages.botResults
Result of a query to an inline bot

```
messages.botResults#e021f2f6 flags:# gallery:flags.0?true query_id:long next_offset:flags.1?string switch_pm:flags.2?InlineBotSwitchPM switch_webview:flags.3?InlineBotWebView results:Vector<BotInlineResult> cache_time:int users:Vector<User> = messages.BotResults;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| gallery | flags.0?true | Whether the result is a picture gallery |
| query_id | long | Query ID |
| next_offset | flags.1?string | The next offset to use when navigating through results |
| switch_pm | flags.2?InlineBotSwitchPM | Shown as a button on top of the remaining inline result list; if clicked, redirects the user to a private chat with the bot with the specified start parameter. |
| switch_webview | flags.3?InlineBotWebView | Shown as a button on top of the remaining inline result list; if clicked, opens the specified inline mode mini app. |
| results | Vector<BotInlineResult> | The results |
| cache_time | int | Caching validity of the results |
| users | Vector<User> | Users mentioned in the results |


## Type
messages.BotResults

## Related pages
