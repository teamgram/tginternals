# bots.toggleUsername
Activate or deactivate a purchased fragment.com username associated to a bot we own.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.toggleUsername#53ca973 bot:InputUser username:string active:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The bot |
| username | string | Username |
| active | Bool | Whether to activate or deactivate it |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

