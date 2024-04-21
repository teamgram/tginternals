# bots.getBotInfo
Get localized name, about text and description of a bot (or of the current account, if called by a bot).

```
bots.botInfo#e8a775b0 name:string about:string description:string = bots.BotInfo;
---functions---
bots.getBotInfo#dcd914fd flags:# bot:flags.0?InputUser lang_code:string = bots.BotInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| bot | flags.0?InputUser | If called by a user, must contain the peer of a bot we own. |
| lang_code | string | Language code, if left empty this method will return the fallback about text and description. |


## Result
bots.BotInfo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LANG_CODE_INVALID | The specified language code is invalid. |
| 400 | USER_BOT_INVALID | User accounts must provide the bot method parameter when calling this method. If there is no such method parameter, this method can only be invoked by bot accounts. |

