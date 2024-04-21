# storyFwdHeader
Contains info about the original poster of a reposted story.

```
storyFwdHeader#b826e150 flags:# modified:flags.3?true from:flags.0?Peer from_name:flags.1?string story_id:flags.2?int = StoryFwdHeader;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| modified | flags.3?true | Whether the story media was modified before reposting it (for example by overlaying a round video with a reaction). |
| from | flags.0?Peer | Peer that originally posted the story; will be empty for stories forwarded from a user with forwards privacy enabled, in which case from_name will be set, instead. |
| from_name | flags.1?string | Will be set for stories forwarded from a user with forwards privacy enabled, in which case from will also be empty. |
| story_id | flags.2?int | , contains the story ID |


## Type
StoryFwdHeader

## Related pages
