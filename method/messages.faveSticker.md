# messages.faveSticker
Mark or unmark a sticker as favorite

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.faveSticker#b9ffc55b id:InputDocument unfave:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | InputDocument | Sticker in question |
| unfave | Bool | Whether to add or remove a sticker from favorites |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STICKER_ID_INVALID | The provided sticker ID is invalid. |

