# messages.requestAppWebView
Open a bot mini app from a direct Mini App deep link, sending over user information after user confirmation.

```
webViewResultUrl#4d22ff98 flags:# fullsize:flags.1?true fullscreen:flags.2?true query_id:flags.0?long url:string = WebViewResult;
---functions---
messages.requestAppWebView#53618bce flags:# write_allowed:flags.0?true compact:flags.7?true fullscreen:flags.8?true peer:InputPeer app:InputBotApp start_param:flags.1?string theme_params:flags.2?DataJSON platform:string = WebViewResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| write_allowed | flags.0?true | Set this flag if the bot is asking permission to send messages to the user as specified in the direct Mini App deep link docs, and the user agreed. |
| compact | flags.7?true | If set, requests to open the mini app in compact mode (as opposed to normal or fullscreen mode). Must be set if the mode parameter of the direct Mini App deep link is equal to compact. |
| fullscreen | flags.8?true | If set, requests to open the mini app in fullscreen mode (as opposed to compact or normal mode). Must be set if the mode parameter of the direct Mini App deep link is equal to fullscreen. |
| peer | InputPeer | If the client has clicked on the link in a Telegram chat, pass the chat's peer information; otherwise pass the bot's peer information, instead. |
| app | InputBotApp | The app obtained by invoking messages.getBotApp as specified in the direct Mini App deep link docs. |
| start_param | flags.1?string | If the startapp query string parameter is present in the direct Mini App deep link, pass it to start_param. |
| theme_params | flags.2?DataJSON | Theme parameters » |
| platform | string | Short name of the application; 0-64 English letters, digits, and underscores |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_APP_BOT_INVALID | The bot_id passed in the inputBotAppShortName constructor is invalid. |
| 400 | BOT_APP_INVALID | The specified bot app is invalid. |
| 400 | BOT_APP_SHORTNAME_INVALID | The specified bot app short name is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | THEME_PARAMS_INVALID | The specified theme_params field is invalid. |

