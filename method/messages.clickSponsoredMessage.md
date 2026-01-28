# messages.clickSponsoredMessage
Informs the server that the user has interacted with a sponsored message in one of the ways listed here ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.clickSponsoredMessage#8235057e flags:# media:flags.0?true fullscreen:flags.1?true random_id:bytes = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| media | flags.0?true | The user clicked on the media |
| fullscreen | flags.1?true | The user expanded the video to full screen, and then clicked on it. |
| random_id | bytes | The ad's unique ID. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

