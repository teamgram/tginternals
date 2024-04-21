# dialog
Chat

```
dialog#d58a08c6 flags:# pinned:flags.2?true unread_mark:flags.3?true view_forum_as_messages:flags.6?true peer:Peer top_message:int read_inbox_max_id:int read_outbox_max_id:int unread_count:int unread_mentions_count:int unread_reactions_count:int notify_settings:PeerNotifySettings pts:flags.0?int draft:flags.1?DraftMessage folder_id:flags.4?int ttl_period:flags.5?int = Dialog;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| pinned | flags.2?true | Is the dialog pinned |
| unread_mark | flags.3?true | Whether the chat was manually marked as unread |
| view_forum_as_messages | flags.6?true | Users may also choose to display messages from all topics of a forum as if they were sent to a normal group, using a "View as messages" setting in the local client.  This setting only affects the current account, and is synced to other logged in sessions using the channels.toggleViewForumAsMessages method; invoking this method will update the value of this flag. |
| peer | Peer | The chat |
| top_message | int | The latest message ID |
| read_inbox_max_id | int | Position up to which all incoming messages are read. |
| read_outbox_max_id | int | Position up to which all outgoing messages are read. |
| unread_count | int | Number of unread messages |
| unread_mentions_count | int | Number of unread mentions |
| unread_reactions_count | int | Number of unread reactions to messages you sent |
| notify_settings | PeerNotifySettings | Notification settings |
| pts | flags.0?int | PTS |
| draft | flags.1?DraftMessage | Message draft |
| folder_id | flags.4?int | Peer folder ID, for more info click here |
| ttl_period | flags.5?int | Time-to-live of all messages sent in this dialog |


## Type
Dialog

## Related pages
