# stories.Stories
List of stories

```
stories.stories#63c3dd0a flags:# count:int stories:Vector<StoryItem> pinned_to_top:flags.0?Vector<int> chats:Vector<Chat> users:Vector<User> = stories.Stories;

---functions---

stories.getPinnedStories#5821a5dc peer:InputPeer offset_id:int limit:int = stories.Stories;
stories.getStoriesArchive#b4352016 peer:InputPeer offset_id:int limit:int = stories.Stories;
stories.getStoriesByID#5774ca74 peer:InputPeer id:Vector<int> = stories.Stories;
stories.getAlbumStories#ac806d61 peer:InputPeer album_id:int offset:int limit:int = stories.Stories;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| stories.stories | List of stories |


## Methods
| Method | Description |
| ---- | ----------- |
| stories.getPinnedStories | Fetch the stories pinned on a peer's profile. |
| stories.getStoriesArchive | Fetch the story archive » of a peer we control. |
| stories.getStoriesByID | Obtain full info about a set of stories by their IDs. |
| stories.getAlbumStories | Get stories in a story album ». |


