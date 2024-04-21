# messages.getBotCallbackAnswer
Press an inline callback button and get a callback answer from the bot

```
messages.botCallbackAnswer#36585ea4 flags:# alert:flags.1?true has_url:flags.3?true native_ui:flags.4?true message:flags.0?string url:flags.2?string cache_time:int = messages.BotCallbackAnswer;
---functions---
messages.getBotCallbackAnswer#9342ca07 flags:# game:flags.1?true peer:InputPeer msg_id:int data:flags.0?bytes password:flags.2?InputCheckPasswordSRP = messages.BotCallbackAnswer;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| game | flags.1?true | Whether this is a "play game" button |
| peer | InputPeer | Where was the inline keyboard sent |
| msg_id | int | ID of the Message with the inline keyboard |
| data | flags.0?bytes | Callback data |
| password | flags.2?InputCheckPasswordSRP | For buttons requiring you to verify your identity with your 2FA password, the SRP payload generated using SRP. |


## Result
messages.BotCallbackAnswer

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_RESPONSE_TIMEOUT | A timeout occurred while fetching data from the bot. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | DATA_INVALID | Encrypted data invalid. |
| 400 | MESSAGE_ID_INVALID | The provided message id is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| -503 | Timeout | Timeout while fetching data. |

