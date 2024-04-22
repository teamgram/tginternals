# StoryItem
Represents a Telegram Story

```
storyItemDeleted#51e6ee4f id:int = StoryItem;
storyItemSkipped#ffadc913 flags:# close_friends:flags.8?true id:int date:int expire_date:int = StoryItem;
storyItem#af6365a1 flags:# pinned:flags.5?true public:flags.7?true close_friends:flags.8?true min:flags.9?true noforwards:flags.10?true edited:flags.11?true contacts:flags.12?true selected_contacts:flags.13?true out:flags.16?true id:int date:int fwd_from:flags.17?StoryFwdHeader expire_date:int caption:flags.0?string entities:flags.1?Vector<MessageEntity> media:MessageMedia media_areas:flags.14?Vector<MediaArea> privacy:flags.2?Vector<PrivacyRule> views:flags.3?StoryViews sent_reaction:flags.15?Reaction = StoryItem;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| storyItemDeleted | Represents a previously active story, that was deleted |
| storyItemSkipped | Represents an active story, whose full information was omitted for space and performance reasons; use stories.getStoriesByID to fetch full info about the skipped story when and if needed. |
| storyItem | Represents a story. |


## Methods
| Method | Description |
| ---- | ----------- |


