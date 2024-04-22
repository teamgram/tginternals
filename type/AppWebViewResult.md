# AppWebViewResult
Contains the link that must be used to open a direct link Mini App.

```
appWebViewResultUrl#3c1b4f0d url:string = AppWebViewResult;

---functions---

messages.requestAppWebView#8c5a3b3c flags:# write_allowed:flags.0?true peer:InputPeer app:InputBotApp start_param:flags.1?string theme_params:flags.2?DataJSON platform:string = AppWebViewResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| appWebViewResultUrl | Contains the link that must be used to open a direct link Mini App. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.requestAppWebView | Open a bot mini app from a direct Mini App deep link, sending over user information after user confirmation.After calling this method, until the user closes the webview, messages.prolongWebView must be called every 60 seconds. |


