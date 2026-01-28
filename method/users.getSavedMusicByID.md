# users.getSavedMusicByID
Check if the passed songs are still pinned to the user's profile, or refresh the file references of songs pinned on a user's profile see here » for more info.

```
users.savedMusicNotModified#e3878aa4 count:int = users.SavedMusic;
users.savedMusic#34a2f297 count:int documents:Vector<Document> = users.SavedMusic;
---functions---
users.getSavedMusicByID#7573a4e9 id:InputUser documents:Vector<InputDocument> = users.SavedMusic;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | InputUser | The ID of the user. |
| documents | Vector<InputDocument> | The songs (here, file_reference can be empty to refresh file references). |


## Result
users.SavedMusic

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

