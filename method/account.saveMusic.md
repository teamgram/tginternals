# account.saveMusic
Adds or removes a song from the current user's profile see here » for more info on the music tab of the profile page.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.saveMusic#b26732a9 flags:# unsave:flags.0?true id:InputDocument after_id:flags.1?InputDocument = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| unsave | flags.0?true | If set, removes the song. |
| id | InputDocument | The song to add or remove; can be an already added song when reordering songs with after_id. Adding an already added song will never re-add it, only move it to the top of the song list (or after the song passed in after_id). |
| after_id | flags.1?InputDocument | If set, the song will be added after the passed song (must be already pinned on the profile). |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DOCUMENT_INVALID | The specified document is invalid. |

