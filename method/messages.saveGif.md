# messages.saveGif
Add GIF to saved gifs list

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.saveGif#327a30cb id:InputDocument unsave:Bool = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | InputDocument | GIF to save |
| unsave | Bool | Whether to remove GIF from saved gifs list |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | GIF_ID_INVALID | The provided GIF ID is invalid. |

