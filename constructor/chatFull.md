# chatFull
Full info about a basic group.

```
chatFull#c9d31138 flags:# can_set_username:flags.7?true has_scheduled:flags.8?true translations_disabled:flags.19?true id:long about:string participants:ChatParticipants chat_photo:flags.2?Photo notify_settings:PeerNotifySettings exported_invite:flags.13?ExportedChatInvite bot_info:flags.3?Vector<BotInfo> pinned_msg_id:flags.6?int folder_id:flags.11?int call:flags.12?InputGroupCall ttl_period:flags.14?int groupcall_default_join_as:flags.15?Peer theme_emoticon:flags.16?string requests_pending:flags.17?int recent_requesters:flags.17?Vector<long> available_reactions:flags.18?ChatReactions = ChatFull;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| can_set_username | flags.7?true | Can we change the username of this chat |
| has_scheduled | flags.8?true | Whether scheduled messages are available |
| translations_disabled | flags.19?true | Whether the real-time chat translation popup should be hidden. |
| id | long | ID of the chat |
| about | string | About string for this chat |
| participants | ChatParticipants | Participant list |
| chat_photo | flags.2?Photo | Chat photo |
| notify_settings | PeerNotifySettings | Notification settings |
| exported_invite | flags.13?ExportedChatInvite | Chat invite |
| bot_info | flags.3?Vector<BotInfo> | Info about bots that are in this chat |
| pinned_msg_id | flags.6?int | Message ID of the last pinned message |
| folder_id | flags.11?int | Peer folder ID, for more info click here |
| call | flags.12?InputGroupCall | Group call information |
| ttl_period | flags.14?int | Time-To-Live of messages sent by the current user to this chat |
| groupcall_default_join_as | flags.15?Peer | When using phone.getGroupCallJoinAs to get a list of peers that can be used to join a group call, this field indicates the peer that should be selected by default. |
| theme_emoticon | flags.16?string | Emoji representing a specific chat theme |
| requests_pending | flags.17?int | Pending join requests » |
| recent_requesters | flags.17?Vector<long> | IDs of users who requested to join recently |
| available_reactions | flags.18?ChatReactions | Allowed message reactions » |


## Type
ChatFull

## Related pages
