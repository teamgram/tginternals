# messages.updateSavedReactionTag
Update the description of a saved message tag ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.updateSavedReactionTag#60297dec flags:# reaction:Reaction title:flags.0?string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| reaction | Reaction | Reaction associated to the tag |
| title | flags.0?string | Tag description, max 12 UTF-8 characters; to remove the description call the method without setting this flag. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |
| 400 | REACTION_INVALID | The specified reaction is invalid. |

