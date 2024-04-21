# messages.requestAppWebView
Open a bot mini app from a direct Mini App deep link, sending over user information after user confirmation.

```
appWebViewResultUrl#3c1b4f0d url:string = AppWebViewResult;
---functions---
messages.requestAppWebView#8c5a3b3c flags:# write_allowed:flags.0?true peer:InputPeer app:InputBotApp start_param:flags.1?string theme_params:flags.2?DataJSON platform:string = AppWebViewResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| write_allowed | flags.0?true | Set this flag if the bot is asking permission to send messages to the user as specified in the direct Mini App deep link docs, and the user agreed. |
| peer | InputPeer | If the client has clicked on the link in a Telegram chat, pass the chat's peer information; otherwise pass the bot's peer information, instead. |
| app | InputBotApp | The app obtained by invoking messages.getBotApp as specified in the direct Mini App deep link docs. |
| start_param | flags.1?string | If the startapp query string parameter is present in the direct Mini App deep link, pass it to start_param. |
| theme_params | flags.2?DataJSON | Theme parameters » |
| platform | string | Short name of the application; 0-64 English letters, digits, and underscores |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_APP_INVALID | The specified bot app is invalid. |
| 400 | BOT_APP_SHORTNAME_INVALID | The specified bot app short name is invalid. |

