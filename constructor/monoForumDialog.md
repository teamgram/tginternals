# monoForumDialog
Represents a monoforum topic ».

```
monoForumDialog#64407ea7 flags:# unread_mark:flags.3?true nopaid_messages_exception:flags.4?true peer:Peer top_message:int read_inbox_max_id:int read_outbox_max_id:int unread_count:int unread_reactions_count:int draft:flags.1?DraftMessage = SavedDialog;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| unread_mark | flags.3?true | Whether this topic has a manually set (with messages.markDialogUnread) unread mark. |
| nopaid_messages_exception | flags.4?true | If set, an admin has exempted this peer from payment to send messages using account.toggleNoPaidMessagesException. |
| peer | Peer | The peer associated to the topic, AKA the topic ID. |
| top_message | int | The latest message ID |
| read_inbox_max_id | int | Position up to which all incoming messages are read. |
| read_outbox_max_id | int | Position up to which all outgoing messages are read. |
| unread_count | int | Number of unread messages. |
| unread_reactions_count | int | Number of unread reactions. |
| draft | flags.1?DraftMessage | A pending message draft. |


## Type
SavedDialog

## Related pages
