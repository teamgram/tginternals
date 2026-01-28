# users.getSavedMusic
Get songs pinned to the user's profile, see here » for more info.

```
users.savedMusicNotModified#e3878aa4 count:int = users.SavedMusic;
users.savedMusic#34a2f297 count:int documents:Vector<Document> = users.SavedMusic;
---functions---
users.getSavedMusic#788d7fe3 id:InputUser offset:int limit:int hash:long = users.SavedMusic;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | InputUser | The ID of the user. |
| offset | int | Offset for pagination. |
| limit | int | Maximum number of results to return, see pagination |
| hash | long | Hash » of the IDs of previously added songs, to avoid returning any result if there was no change. |


## Result
users.SavedMusic

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

