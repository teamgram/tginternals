# bots.resetBotCommands
Clear bot commands for the specified bot scope and language code

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.resetBotCommands#3d8de0f9 scope:BotCommandScope lang_code:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| scope | BotCommandScope | Command scope |
| lang_code | string | Language code |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | LANG_CODE_INVALID | The specified language code is invalid. |

