# messages.requestSimpleWebView
Open a bot mini app.

```
webViewResultUrl#4d22ff98 flags:# fullsize:flags.1?true fullscreen:flags.2?true query_id:flags.0?long url:string = WebViewResult;
---functions---
messages.requestSimpleWebView#413a3e73 flags:# from_switch_webview:flags.1?true from_side_menu:flags.2?true compact:flags.7?true fullscreen:flags.8?true bot:InputUser url:flags.3?string start_param:flags.4?string theme_params:flags.0?DataJSON platform:string = WebViewResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| from_switch_webview | flags.1?true | Whether the webapp was opened by clicking on the switch_webview button shown on top of the inline results list returned by messages.getInlineBotResults. |
| from_side_menu | flags.2?true | Set this flag if opening the Mini App from the installed side menu entry ». |
| compact | flags.7?true | Deprecated. |
| fullscreen | flags.8?true | Requests to open the app in fullscreen mode. |
| bot | InputUser | Bot that owns the mini app |
| url | flags.3?string | Web app URL, if opening from a keyboard button or inline result |
| start_param | flags.4?string | Deprecated. |
| theme_params | flags.0?DataJSON | Theme parameters » |
| platform | string | Short name of the application; 0-64 English letters, digits, and underscores |


## Result
WebViewResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |
| 400 | URL_INVALID | Invalid URL provided. |

