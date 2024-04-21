# messages.getBotApp
Obtain information about a direct link Mini App

```
messages.botApp#eb50adf5 flags:# inactive:flags.0?true request_write_access:flags.1?true has_settings:flags.2?true app:BotApp = messages.BotApp;
---functions---
messages.getBotApp#34fdc5c3 app:InputBotApp hash:long = messages.BotApp;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| app | InputBotApp | Bot app information obtained from a Direct Mini App deep link ». |
| hash | long | Hash for pagination, for more info click here |


## Result
messages.BotApp

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_APP_INVALID | The specified bot app is invalid. |

