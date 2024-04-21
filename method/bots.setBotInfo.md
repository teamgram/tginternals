# bots.setBotInfo
Set localized name, about text and description of a bot (or of the current account, if called by a bot).

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.setBotInfo#10cf3123 flags:# bot:flags.2?InputUser lang_code:string name:flags.3?string about:flags.0?string description:flags.1?string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| bot | flags.2?InputUser | If called by a user, must contain the peer of a bot we own. |
| lang_code | string | Language code, if left empty update the fallback about text and description |
| name | flags.3?string | New bot name |
| about | flags.0?string | New about text |
| description | flags.1?string | New description |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USER_BOT_INVALID | User accounts must provide the bot method parameter when calling this method. If there is no such method parameter, this method can only be invoked by bot accounts. |

