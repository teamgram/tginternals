# messages.requestSimpleWebView
Open a bot mini app.

```
simpleWebViewResultUrl#882f76bb url:string = SimpleWebViewResult;
---functions---
messages.requestSimpleWebView#1a46500a flags:# from_switch_webview:flags.1?true from_side_menu:flags.2?true bot:InputUser url:flags.3?string start_param:flags.4?string theme_params:flags.0?DataJSON platform:string = SimpleWebViewResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| from_switch_webview | flags.1?true | Whether the webapp was opened by clicking on the switch_webview button shown on top of the inline results list returned by messages.getInlineBotResults. |
| from_side_menu | flags.2?true | Set this flag if opening the Mini App from the installed side menu entry » or from a Mini App link ». |
| bot | InputUser | Bot that owns the mini app |
| url | flags.3?string | Web app URL, if opening from a keyboard button or inline result |
| start_param | flags.4?string | Start parameter, if opening from a Mini App link ». |
| theme_params | flags.0?DataJSON | Theme parameters » |
| platform | string | Short name of the application; 0-64 English letters, digits, and underscores |


## Result
SimpleWebViewResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

