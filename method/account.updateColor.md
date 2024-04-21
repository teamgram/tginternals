# account.updateColor
Update the accent color and background custom emoji » of the current account.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.updateColor#7cefa15d flags:# for_profile:flags.1?true color:flags.2?int background_emoji_id:flags.0?long = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| for_profile | flags.1?true | Whether to change the accent color emoji pattern of the profile page; otherwise, the accent color and emoji pattern of messages will be changed. |
| color | flags.2?int | ID of the accent color palette » to use (not RGB24, see here » for more info). |
| background_emoji_id | flags.0?long | Custom emoji ID used in the accent color pattern. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | COLOR_INVALID | The specified color palette ID was invalid. |

