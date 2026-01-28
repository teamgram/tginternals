# WebViewResult
Contains the webview URL with appropriate theme and user info parameters added

```
webViewResultUrl#4d22ff98 flags:# fullsize:flags.1?true fullscreen:flags.2?true query_id:flags.0?long url:string = WebViewResult;

---functions---

messages.requestWebView#269dc2c1 flags:# from_bot_menu:flags.4?true silent:flags.5?true compact:flags.7?true fullscreen:flags.8?true peer:InputPeer bot:InputUser url:flags.1?string start_param:flags.3?string theme_params:flags.2?DataJSON platform:string reply_to:flags.0?InputReplyTo send_as:flags.13?InputPeer = WebViewResult;
messages.requestSimpleWebView#413a3e73 flags:# from_switch_webview:flags.1?true from_side_menu:flags.2?true compact:flags.7?true fullscreen:flags.8?true bot:InputUser url:flags.3?string start_param:flags.4?string theme_params:flags.0?DataJSON platform:string = WebViewResult;
messages.requestAppWebView#53618bce flags:# write_allowed:flags.0?true compact:flags.7?true fullscreen:flags.8?true peer:InputPeer app:InputBotApp start_param:flags.1?string theme_params:flags.2?DataJSON platform:string = WebViewResult;
messages.requestMainWebView#c9e01e7b flags:# compact:flags.7?true fullscreen:flags.8?true peer:InputPeer bot:InputUser start_param:flags.1?string theme_params:flags.0?DataJSON platform:string = WebViewResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| webViewResultUrl | Contains the webview URL with appropriate theme and user info parameters added |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.requestWebView | Open a bot mini app, sending over user information after user confirmation.After calling this method, until the user closes the webview, messages.prolongWebView must be called every 60 seconds. |
| messages.requestSimpleWebView | Open a bot mini app. |
| messages.requestAppWebView | Open a bot mini app from a direct Mini App deep link, sending over user information after user confirmation.After calling this method, until the user closes the webview, messages.prolongWebView must be called every 60 seconds. |
| messages.requestMainWebView | Open a Main Mini App. |


