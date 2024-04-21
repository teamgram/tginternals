# bots.getBotCommands
Obtain a list of bot commands for the specified bot scope and language code

```
---functions---
bots.getBotCommands#e34c0dd6 scope:BotCommandScope lang_code:string = Vector<BotCommand>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| scope | BotCommandScope | Command scope |
| lang_code | string | Language code |


## Result
Vector<BotCommand>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USER_BOT_INVALID | User accounts must provide the bot method parameter when calling this method. If there is no such method parameter, this method can only be invoked by bot accounts. |

