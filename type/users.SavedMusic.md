# users.SavedMusic
List of songs (document.ids) currently pinned on a user's profile, see here » for more info.

```
users.savedMusicNotModified#e3878aa4 count:int = users.SavedMusic;
users.savedMusic#34a2f297 count:int documents:Vector<Document> = users.SavedMusic;

---functions---

users.getSavedMusic#788d7fe3 id:InputUser offset:int limit:int hash:long = users.SavedMusic;
users.getSavedMusicByID#7573a4e9 id:InputUser documents:Vector<InputDocument> = users.SavedMusic;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| users.savedMusicNotModified | This subset of the songs currently pinned on a user's profile hasn't changed, see here » for more info. |
| users.savedMusic | List of songs currently pinned on a user's profile, see here » for more info. |


## Methods
| Method | Description |
| ---- | ----------- |
| users.getSavedMusic | Get songs pinned to the user's profile, see here » for more info. |
| users.getSavedMusicByID | Check if the passed songs are still pinned to the user's profile, or refresh the file references of songs pinned on a user's profile see here » for more info. |


