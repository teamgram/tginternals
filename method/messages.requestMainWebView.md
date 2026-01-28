# messages.requestMainWebView
Open a Main Mini App.

```
webViewResultUrl#4d22ff98 flags:# fullsize:flags.1?true fullscreen:flags.2?true query_id:flags.0?long url:string = WebViewResult;
---functions---
messages.requestMainWebView#c9e01e7b flags:# compact:flags.7?true fullscreen:flags.8?true peer:InputPeer bot:InputUser start_param:flags.1?string theme_params:flags.0?DataJSON platform:string = WebViewResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| compact | flags.7?true | If set, requests to open the mini app in compact mode (as opposed to normal or fullscreen mode). Must be set if the mode parameter of the Main Mini App link is equal to compact. |
| fullscreen | flags.8?true | If set, requests to open the mini app in fullscreen mode (as opposed to compact or normal mode). Must be set if the mode parameter of the Main Mini App link is equal to fullscreen. |
| peer | InputPeer | Currently open chat, may be inputPeerEmpty if no chat is currently open. |
| bot | InputUser | Bot that owns the main mini app. |
| start_param | flags.1?string | Start parameter, if opening from a Main Mini App link ». |
| theme_params | flags.0?DataJSON | Theme parameters » |
| platform | string | Short name of the application; 0-64 English letters, digits, and underscores |


## Result
WebViewResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

