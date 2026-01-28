# reactionsNotifySettings
Reaction notification settings, see here » for more info.

```
reactionsNotifySettings#56e34970 flags:# messages_notify_from:flags.0?ReactionNotificationsFrom stories_notify_from:flags.1?ReactionNotificationsFrom sound:NotificationSound show_previews:Bool = ReactionsNotifySettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| messages_notify_from | flags.0?ReactionNotificationsFrom | Message reaction notification settings, if not set completely disables notifications/updates about message reactions. |
| stories_notify_from | flags.1?ReactionNotificationsFrom | Story reaction notification settings, if not set completely disables notifications/updates about reactions to stories. |
| sound | NotificationSound | Notification sound for reactions » |
| show_previews | Bool | If false, push notifications » about message/story reactions will only be of type REACT_HIDDEN/REACT_STORY_HIDDEN, without any information about the reacted-to story or the reaction itself. |


## Type
ReactionsNotifySettings

## Related pages
