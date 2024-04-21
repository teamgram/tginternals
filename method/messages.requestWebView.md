# messages.requestWebView
Open a bot mini app, sending over user information after user confirmation.

```
webViewResultUrl#c14557c query_id:long url:string = WebViewResult;
---functions---
messages.requestWebView#269dc2c1 flags:# from_bot_menu:flags.4?true silent:flags.5?true peer:InputPeer bot:InputUser url:flags.1?string start_param:flags.3?string theme_params:flags.2?DataJSON platform:string reply_to:flags.0?InputReplyTo send_as:flags.13?InputPeer = WebViewResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| from_bot_menu | flags.4?true | Whether the webview was opened by clicking on the bot's menu button ». |
| silent | flags.5?true | Whether the inline message that will be sent by the bot on behalf of the user once the web app interaction is terminated should be sent silently (no notifications for the receivers). |
| peer | InputPeer | Dialog where the web app is being opened, and where the resulting message will be sent (see the docs for more info »). |
| bot | InputUser | Bot that owns the web app |
| url | flags.1?string | Web app URL |
| start_param | flags.3?string | If the web app was opened from the attachment menu using a attachment menu deep link, start_param should contain the data from the startattach parameter. |
| theme_params | flags.2?DataJSON | Theme parameters » |
| platform | string | Short name of the application; 0-64 English letters, digits, and underscores |
| reply_to | flags.0?InputReplyTo | If set, indicates that the inline message that will be sent by the bot on behalf of the user once the web app interaction is terminated should be sent in reply to the specified message or story. |
| send_as | flags.13?InputPeer | Open the web app as the specified peer, sending the resulting the message as the specified peer. |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |
| 400 | BOT_WEBVIEW_DISABLED | A webview cannot be opened in the specified conditions: emitted for example if from_bot_menu or url are set and peer is not the chat with the bot. |
| 400 | INPUT_USER_DEACTIVATED | The specified user was deleted. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | YOU_BLOCKED_USER | You blocked this user. |

