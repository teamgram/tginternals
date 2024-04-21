# messages.sendWebViewResultMessage
Terminate webview interaction started with messages.requestWebView, sending the specified message to the chat on behalf of the user.

```
webViewMessageSent#c94511c flags:# msg_id:flags.0?InputBotInlineMessageID = WebViewMessageSent;
---functions---
messages.sendWebViewResultMessage#a4314f5 bot_query_id:string result:InputBotInlineResult = WebViewMessageSent;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot_query_id | string | Webview interaction ID obtained from messages.requestWebView |
| result | InputBotInlineResult | Message to send |


## Result
WebViewMessageSent

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | QUERY_ID_INVALID | The query ID is invalid. |

