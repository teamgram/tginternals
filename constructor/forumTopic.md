# forumTopic
Represents a forum topic.

```
forumTopic#71701da9 flags:# my:flags.1?true closed:flags.2?true pinned:flags.3?true short:flags.5?true hidden:flags.6?true id:int date:int title:string icon_color:int icon_emoji_id:flags.0?long top_message:int read_inbox_max_id:int read_outbox_max_id:int unread_count:int unread_mentions_count:int unread_reactions_count:int from_id:Peer notify_settings:PeerNotifySettings draft:flags.4?DraftMessage = ForumTopic;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| my | flags.1?true | Whether the topic was created by the current user |
| closed | flags.2?true | Whether the topic is closed (no messages can be sent to it) |
| pinned | flags.3?true | Whether the topic is pinned |
| short | flags.5?true | Whether this constructor is a reduced version of the full topic information. If set, only the my, closed, id, date, title, icon_color, icon_emoji_id and from_id parameters will contain valid information. Reduced info is usually only returned in topic-related admin log events » and in the messages.channelMessages constructor: if needed, full information can be fetched using channels.getForumTopicsByID. |
| hidden | flags.6?true | Whether the topic is hidden (only valid for the "General" topic, id=1) |
| id | int | Topic ID |
| date | int | Topic creation date |
| title | string | Topic title |
| icon_color | int | If no custom emoji icon is specified, specifies the color of the fallback topic icon (RGB), one of 0x6FB9F0, 0xFFD67E, 0xCB86DB, 0x8EEE98, 0xFF93B2, or 0xFB6F5F. |
| icon_emoji_id | flags.0?long | ID of the custom emoji used as topic icon. |
| top_message | int | ID of the last message that was sent to this topic |
| read_inbox_max_id | int | Position up to which all incoming messages are read. |
| read_outbox_max_id | int | Position up to which all outgoing messages are read. |
| unread_count | int | Number of unread messages |
| unread_mentions_count | int | Number of unread mentions |
| unread_reactions_count | int | Number of unread reactions to messages you sent |
| from_id | Peer | ID of the peer that created the topic |
| notify_settings | PeerNotifySettings | Notification settings |
| draft | flags.4?DraftMessage | Message draft |


## Type
ForumTopic

## Related pages
