# messages.setDefaultReaction
Change default emoji reaction to use in the quick reaction menu: the value is synced across devices and can be fetched using help.getConfig, reactions_default field.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setDefaultReaction#4f47a016 reaction:Reaction = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| reaction | Reaction | New emoji reaction |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | REACTION_INVALID | The specified reaction is invalid. |

