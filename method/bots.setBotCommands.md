# bots.setBotCommands
Set bot command list

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.setBotCommands#517165a scope:BotCommandScope lang_code:string commands:Vector<BotCommand> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| scope | BotCommandScope | Command scope |
| lang_code | string | Language code |
| commands | Vector<BotCommand> | Bot commands |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_COMMAND_DESCRIPTION_INVALID | The specified command description is invalid. |
| 400 | BOT_COMMAND_INVALID | The specified command is invalid. |
| 400 | LANG_CODE_INVALID | The specified language code is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

