# storyItem
Represents a story.

```
storyItem#af6365a1 flags:# pinned:flags.5?true public:flags.7?true close_friends:flags.8?true min:flags.9?true noforwards:flags.10?true edited:flags.11?true contacts:flags.12?true selected_contacts:flags.13?true out:flags.16?true id:int date:int fwd_from:flags.17?StoryFwdHeader expire_date:int caption:flags.0?string entities:flags.1?Vector<MessageEntity> media:MessageMedia media_areas:flags.14?Vector<MediaArea> privacy:flags.2?Vector<PrivacyRule> views:flags.3?StoryViews sent_reaction:flags.15?Reaction = StoryItem;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pinned | flags.5?true | Whether this story is pinned on the user's profile |
| public | flags.7?true | Whether this story is public and can be viewed by everyone |
| close_friends | flags.8?true | Whether this story can only be viewed by our close friends, see here » for more info |
| min | flags.9?true | Full information about this story was omitted for space and performance reasons; use stories.getStoriesByID to fetch full info about this story when and if needed. |
| noforwards | flags.10?true | Whether this story is protected and thus cannot be forwarded; clients should also prevent users from saving attached media (i.e. videos should only be streamed, photos should be kept in RAM, et cetera). |
| edited | flags.11?true | Indicates whether the story was edited. |
| contacts | flags.12?true | Whether this story can only be viewed by our contacts |
| selected_contacts | flags.13?true | Whether this story can only be viewed by a select list of our contacts |
| out | flags.16?true | indicates whether we sent this story. |
| id | int | ID of the story. |
| date | int | When was the story posted. |
| fwd_from | flags.17?StoryFwdHeader | For reposted stories », contains info about the original story. |
| expire_date | int | When does the story expire. |
| caption | flags.0?string | Story caption. |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text |
| media | MessageMedia | Story media. |
| media_areas | flags.14?Vector<MediaArea> | List of media areas, see here » for more info on media areas. |
| privacy | flags.2?Vector<PrivacyRule> | Privacy rules indicating who can and can't view this story |
| views | flags.3?StoryViews | View date and reaction information |
| sent_reaction | flags.15?Reaction | The reaction we sent. |


## Type
StoryItem

## Related pages
