# messages.toggleBotInAttachMenu
Enable or disable web bot attachment menu »

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.toggleBotInAttachMenu#69f59d69 flags:# write_allowed:flags.0?true bot:InputUser enabled:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| write_allowed | flags.0?true | Whether the user authorizes the bot to write messages to them, if requested by attachMenuBot.request_write_access |
| bot | InputUser | Bot ID |
| enabled | Bool | Toggle |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

