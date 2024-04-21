# WebViewResult
Contains the webview URL with appropriate theme and user info parameters added

```
webViewResultUrl#c14557c query_id:long url:string = WebViewResult;

---functions---

messages.requestWebView#269dc2c1 flags:# from_bot_menu:flags.4?true silent:flags.5?true peer:InputPeer bot:InputUser url:flags.1?string start_param:flags.3?string theme_params:flags.2?DataJSON platform:string reply_to:flags.0?InputReplyTo send_as:flags.13?InputPeer = WebViewResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| webViewResultUrl | Contains the webview URL with appropriate theme and user info parameters added |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.requestWebView | Open a bot mini app, sending over user information after user confirmation.After calling this method, until the user closes the webview, messages.prolongWebView must be called every 60 seconds. |


