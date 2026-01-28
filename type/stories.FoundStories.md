# stories.FoundStories
Stories found using global story search ».

```
stories.foundStories#e2de7737 flags:# count:int stories:Vector<FoundStory> next_offset:flags.0?string chats:Vector<Chat> users:Vector<User> = stories.FoundStories;

---functions---

stories.searchPosts#d1810907 flags:# hashtag:flags.0?string area:flags.1?MediaArea peer:flags.2?InputPeer offset:string limit:int = stories.FoundStories;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| stories.foundStories | Stories found using global story search ». |


## Methods
| Method | Description |
| ---- | ----------- |
| stories.searchPosts | Globally search for stories using a hashtag or a location media area, see here » for more info on the full flow.Either hashtag or area must be set when invoking the method. |


