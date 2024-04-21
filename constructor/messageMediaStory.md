# messageMediaStory
Represents a forwarded story or a story mention.

```
messageMediaStory#68cb6283 flags:# via_mention:flags.1?true peer:Peer id:int story:flags.0?StoryItem = MessageMedia;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| via_mention | flags.1?true | If set, indicates that this someone has mentioned us in this story (i.e. by tagging us in the description) or vice versa, we have mentioned the other peer (if the message is outgoing). |
| peer | Peer | Peer that posted the story. |
| id | int | Story ID |
| story | flags.0?StoryItem | The story itself, if absent fetch it using stories.getStoriesByID and the peer/id parameters specified above. |


## Type
MessageMedia

## Related pages
