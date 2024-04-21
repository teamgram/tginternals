# stories.AllStories
Full list of active (or active and hidden) stories.

```
stories.allStoriesNotModified#1158fe3e flags:# state:string stealth_mode:StoriesStealthMode = stories.AllStories;
stories.allStories#6efc5e81 flags:# has_more:flags.0?true count:int state:string peer_stories:Vector<PeerStories> chats:Vector<Chat> users:Vector<User> stealth_mode:StoriesStealthMode = stories.AllStories;

---functions---

stories.getAllStories#eeb0d625 flags:# next:flags.1?true hidden:flags.2?true state:flags.0?string = stories.AllStories;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| stories.allStoriesNotModified | The list of active (or active and hidden) stories has not changed. |
| stories.allStories | Full list of active (or active and hidden) stories. |


## Methods
| Method | Description |
| ---- | ----------- |
| stories.getAllStories | Fetch the List of active (or active and hidden) stories, see here » for more info on watching stories. |


