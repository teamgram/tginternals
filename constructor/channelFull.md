# channelFull
Full info about a channel, supergroup or gigagroup.

```
channelFull#f2bcb6f flags:# can_view_participants:flags.3?true can_set_username:flags.6?true can_set_stickers:flags.7?true hidden_prehistory:flags.10?true can_set_location:flags.16?true has_scheduled:flags.19?true can_view_stats:flags.20?true blocked:flags.22?true flags2:# can_delete_channel:flags2.0?true antispam:flags2.1?true participants_hidden:flags2.2?true translations_disabled:flags2.3?true stories_pinned_available:flags2.5?true view_forum_as_messages:flags2.6?true id:long about:string participants_count:flags.0?int admins_count:flags.1?int kicked_count:flags.2?int banned_count:flags.2?int online_count:flags.13?int read_inbox_max_id:int read_outbox_max_id:int unread_count:int chat_photo:Photo notify_settings:PeerNotifySettings exported_invite:flags.23?ExportedChatInvite bot_info:Vector<BotInfo> migrated_from_chat_id:flags.4?long migrated_from_max_id:flags.4?int pinned_msg_id:flags.5?int stickerset:flags.8?StickerSet available_min_id:flags.9?int folder_id:flags.11?int linked_chat_id:flags.14?long location:flags.15?ChannelLocation slowmode_seconds:flags.17?int slowmode_next_send_date:flags.18?int stats_dc:flags.12?int pts:int call:flags.21?InputGroupCall ttl_period:flags.24?int pending_suggestions:flags.25?Vector<string> groupcall_default_join_as:flags.26?Peer theme_emoticon:flags.27?string requests_pending:flags.28?int recent_requesters:flags.28?Vector<long> default_send_as:flags.29?Peer available_reactions:flags.30?ChatReactions stories:flags2.4?PeerStories wallpaper:flags2.7?WallPaper = ChatFull;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| can_view_participants | flags.3?true | Can we view the participant list? |
| can_set_username | flags.6?true | Can we set the channel's username? |
| can_set_stickers | flags.7?true | Can we associate a stickerpack to the supergroup? |
| hidden_prehistory | flags.10?true | Is the history before we joined hidden to us? |
| can_set_location | flags.16?true | Can we set the geolocation of this group (for geogroups) |
| has_scheduled | flags.19?true | Whether scheduled messages are available |
| can_view_stats | flags.20?true | Can the user view channel/supergroup statistics |
| blocked | flags.22?true | Whether any anonymous admin of this supergroup was blocked: if set, you won't receive messages from anonymous group admins in discussion replies via @replies |
| flags2 | # | Flags, see TL conditional fields |
| can_delete_channel | flags2.0?true | Can we delete this channel? |
| antispam | flags2.1?true | Whether native antispam functionality is enabled in this supergroup. |
| participants_hidden | flags2.2?true | Whether the participant list is hidden. |
| translations_disabled | flags2.3?true | Whether the real-time chat translation popup should be hidden. |
| stories_pinned_available | flags2.5?true | Whether this user has some pinned stories. |
| view_forum_as_messages | flags2.6?true | Users may also choose to display messages from all topics of a forum as if they were sent to a normal group, using a "View as messages" setting in the local client.  This setting only affects the current account, and is synced to other logged in sessions using the channels.toggleViewForumAsMessages method; invoking this method will update the value of this flag. |
| id | long | ID of the channel |
| about | string | Info about the channel |
| participants_count | flags.0?int | Number of participants of the channel |
| admins_count | flags.1?int | Number of channel admins |
| kicked_count | flags.2?int | Number of users kicked from the channel |
| banned_count | flags.2?int | Number of users banned from the channel |
| online_count | flags.13?int | Number of users currently online |
| read_inbox_max_id | int | Position up to which all incoming messages are read. |
| read_outbox_max_id | int | Position up to which all outgoing messages are read. |
| unread_count | int | Count of unread messages |
| chat_photo | Photo | Channel picture |
| notify_settings | PeerNotifySettings | Notification settings |
| exported_invite | flags.23?ExportedChatInvite | Invite link |
| bot_info | Vector<BotInfo> | Info about bots in the channel/supergroup |
| migrated_from_chat_id | flags.4?long | The chat ID from which this group was migrated |
| migrated_from_max_id | flags.4?int | The message ID in the original chat at which this group was migrated |
| pinned_msg_id | flags.5?int | Message ID of the last pinned message |
| stickerset | flags.8?StickerSet | Associated stickerset |
| available_min_id | flags.9?int | Identifier of a maximum unavailable message in a channel due to hidden history. |
| folder_id | flags.11?int | Peer folder ID, for more info click here |
| linked_chat_id | flags.14?long | ID of the linked discussion chat for channels |
| location | flags.15?ChannelLocation | Location of the geogroup |
| slowmode_seconds | flags.17?int | If specified, users in supergroups will only be able to send one message every slowmode_seconds seconds |
| slowmode_next_send_date | flags.18?int | Indicates when the user will be allowed to send another message in the supergroup (unixtime) |
| stats_dc | flags.12?int | If set, specifies the DC to use for fetching channel statistics |
| pts | int | Latest PTS for this channel |
| call | flags.21?InputGroupCall | Livestream or group call information |
| ttl_period | flags.24?int | Time-To-Live of messages in this channel or supergroup |
| pending_suggestions | flags.25?Vector<string> | A list of suggested actions for the supergroup admin, see here for more info ». |
| groupcall_default_join_as | flags.26?Peer | When using phone.getGroupCallJoinAs to get a list of peers that can be used to join a group call, this field indicates the peer that should be selected by default. |
| theme_emoticon | flags.27?string | Emoji representing a specific chat theme |
| requests_pending | flags.28?int | Pending join requests » |
| recent_requesters | flags.28?Vector<long> | IDs of users who requested to join recently |
| default_send_as | flags.29?Peer | Default peer used for sending messages to this channel |
| available_reactions | flags.30?ChatReactions | Allowed message reactions » |
| stories | flags2.4?PeerStories | Channel stories |
| wallpaper | flags2.7?WallPaper | Wallpaper |


## Type
ChatFull

## Related pages
