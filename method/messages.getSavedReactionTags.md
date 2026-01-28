# messages.getSavedReactionTags
Fetch the full list of saved message tags created by the user.

```
messages.savedReactionTagsNotModified#889b59ef = messages.SavedReactionTags;
messages.savedReactionTags#3259950a tags:Vector<SavedReactionTag> hash:long = messages.SavedReactionTags;
---functions---
messages.getSavedReactionTags#3637e05b flags:# peer:flags.0?InputPeer hash:long = messages.SavedReactionTags;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | flags.0?InputPeer | If set, returns tags only used in the specified saved message dialog. |
| hash | long | Hash used for caching, for more info click here. |


## Result
messages.SavedReactionTags

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

