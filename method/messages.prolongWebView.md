# messages.prolongWebView
Indicate to the server (from the user side) that the user is still using a web app.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.prolongWebView#b0d81a83 flags:# silent:flags.5?true peer:InputPeer bot:InputUser query_id:long reply_to:flags.0?InputReplyTo send_as:flags.13?InputPeer = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| silent | flags.5?true | Whether the inline message that will be sent by the bot on behalf of the user once the web app interaction is terminated should be sent silently (no notifications for the receivers). |
| peer | InputPeer | Dialog where the web app was opened. |
| bot | InputUser | Bot that owns the web app |
| query_id | long | Web app interaction ID obtained from messages.requestWebView |
| reply_to | flags.0?InputReplyTo | If set, indicates that the inline message that will be sent by the bot on behalf of the user once the web app interaction is terminated should be sent in reply to the specified message or story. |
| send_as | flags.13?InputPeer | Open the web app as the specified peer |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

