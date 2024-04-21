# messageActionTopicEdit
Forum topic information was edited.

```
messageActionTopicEdit#c0944820 flags:# title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| title | flags.0?string | New topic title. |
| icon_emoji_id | flags.1?long | ID of the new custom emoji used as topic icon, or if it was removed. |
| closed | flags.2?Bool | Whether the topic was opened or closed. |
| hidden | flags.3?Bool | Whether the topic was hidden or unhidden (only valid for the "General" topic, id=1). |


## Type
MessageAction

## Related pages
