# contacts.setBlocked
Replace the contents of an entire blocklist, see here for more info ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
contacts.setBlocked#94c65c76 flags:# my_stories_from:flags.0?true id:Vector<InputPeer> limit:int = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| my_stories_from | flags.0?true | Whether to edit the story blocklist; if not set, will edit the main blocklist. See here » for differences between the two. |
| id | Vector<InputPeer> | Full content of the blocklist. |
| limit | int | Maximum number of results to return, see pagination |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

