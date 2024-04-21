# WebViewMessageSent
Contains information about an inline message sent by a Web App on behalf of a user.

```
webViewMessageSent#c94511c flags:# msg_id:flags.0?InputBotInlineMessageID = WebViewMessageSent;

---functions---

messages.sendWebViewResultMessage#a4314f5 bot_query_id:string result:InputBotInlineResult = WebViewMessageSent;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| webViewMessageSent | Info about a sent inline webview message |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.sendWebViewResultMessage | Terminate webview interaction started with messages.requestWebView, sending the specified message to the chat on behalf of the user. |


