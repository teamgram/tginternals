# stories.CanSendStoryCount
Contains the number of available active story slots (equal to the value of the story_expiring_limit_* client configuration parameter minus the number of currently active stories).

```
stories.canSendStoryCount#c387c04e count_remains:int = stories.CanSendStoryCount;

---functions---

stories.canSendStory#30eb63f0 peer:InputPeer = stories.CanSendStoryCount;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| stories.canSendStoryCount | Contains the number of available active story slots (equal to the value of the story_expiring_limit_* client configuration parameter minus the number of currently active stories). |


## Methods
| Method | Description |
| ---- | ----------- |
| stories.canSendStory | Check whether we can post stories as the specified peer. |


