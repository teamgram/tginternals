# stories.StoryViewsList
Reaction and view counters for a story

```
stories.storyViewsList#59d78fc5 flags:# count:int views_count:int forwards_count:int reactions_count:int views:Vector<StoryView> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?string = stories.StoryViewsList;

---functions---

stories.getStoryViewsList#7ed23c57 flags:# just_contacts:flags.0?true reactions_first:flags.2?true forwards_first:flags.3?true peer:InputPeer q:flags.1?string id:int offset:string limit:int = stories.StoryViewsList;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| stories.storyViewsList | Reaction and view counters for a story |


## Methods
| Method | Description |
| ---- | ----------- |
| stories.getStoryViewsList | Obtain the list of users that have viewed a specific story we posted |


