# account.saveAutoSaveSettings
Modify autosave settings

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.saveAutoSaveSettings#d69b8361 flags:# users:flags.0?true chats:flags.1?true broadcasts:flags.2?true peer:flags.3?InputPeer settings:AutoSaveSettings = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| users | flags.0?true | Whether the new settings should affect all private chats |
| chats | flags.1?true | Whether the new settings should affect all groups |
| broadcasts | flags.2?true | Whether the new settings should affect all channels |
| peer | flags.3?InputPeer | Whether the new settings should affect a specific peer |
| settings | AutoSaveSettings | The new autosave settings |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

