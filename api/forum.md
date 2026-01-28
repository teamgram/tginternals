# Forums

Telegram allows creating forums with multiple distinct topics.

### Forums

```
channel#fe685355 flags:# creator:flags.0?true left:flags.2?true broadcast:flags.5?true verified:flags.7?true megagroup:flags.8?true restricted:flags.9?true signatures:flags.11?true min:flags.12?true scam:flags.19?true has_link:flags.20?true has_geo:flags.21?true slowmode_enabled:flags.22?true call_active:flags.23?true call_not_empty:flags.24?true fake:flags.25?true gigagroup:flags.26?true noforwards:flags.27?true join_to_send:flags.28?true join_request:flags.29?true forum:flags.30?true flags2:# stories_hidden:flags2.1?true stories_hidden_min:flags2.2?true stories_unavailable:flags2.3?true signature_profiles:flags2.12?true autotranslation:flags2.15?true broadcast_messages_allowed:flags2.16?true monoforum:flags2.17?true forum_tabs:flags2.19?true id:long access_hash:flags.13?long title:string username:flags.6?string photo:ChatPhoto date:int restriction_reason:flags.9?Vector<RestrictionReason> admin_rights:flags.14?ChatAdminRights banned_rights:flags.15?ChatBannedRights default_banned_rights:flags.18?ChatBannedRights participants_count:flags.17?int usernames:flags2.0?Vector<Username> stories_max_id:flags2.4?int color:flags2.7?PeerColor profile_color:flags2.8?PeerColor emoji_status:flags2.9?EmojiStatus level:flags2.10?int subscription_until_date:flags2.11?int bot_verification_icon:flags2.13?long send_paid_messages_stars:flags2.14?long linked_monoforum_id:flags2.18?long = Chat;

---functions---

channels.createChannel#91006707 flags:# broadcast:flags.0?true megagroup:flags.1?true for_import:flags.3?true forum:flags.5?true title:string about:string geo_point:flags.2?InputGeoPoint address:flags.2?string ttl_period:flags.4?int = Updates;

channels.toggleForum#3ff75734 channel:InputChannel enabled:Bool tabs:Bool = Updates;
```

Forums may be created either by invoking channels.createChannel with the forum flag set, or by converting an existing supergroup into a forum using channels.toggleForum with enabled=true.
If the group is a basic group, it should be upgraded to a supergroup before converting it into a forum.

Forums can also be converted back to supergroups using channels.toggleForum with enabled=false.

Note that the channels.toggleForum method can only be invoked by admins with owner rights.

Forums have the channel.forum flag set, and conversation happens in distinct forum topics.

#### Forum topics

```
forumTopic#71701da9 flags:# my:flags.1?true closed:flags.2?true pinned:flags.3?true short:flags.5?true hidden:flags.6?true id:int date:int title:string icon_color:int icon_emoji_id:flags.0?long top_message:int read_inbox_max_id:int read_outbox_max_id:int unread_count:int unread_mentions_count:int unread_reactions_count:int from_id:Peer notify_settings:PeerNotifySettings draft:flags.4?DraftMessage = ForumTopic;
forumTopicDeleted#023f109b id:int = ForumTopic;

messages.forumTopics#367617d3 flags:# order_by_create_date:flags.0?true count:int topics:Vector<ForumTopic> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> pts:int = messages.ForumTopics;

inputStickerSetEmojiDefaultTopicIcons#44c1f8e9 = InputStickerSet;

messageActionTopicCreate#0d999256 flags:# title:string icon_color:int icon_emoji_id:flags.0?long = MessageAction;
messageActionTopicEdit#c0944820 flags:# title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = MessageAction;

updateChannelPinnedTopic#192efbe3 flags:# pinned:flags.0?true channel_id:long topic_id:int = Update;
updateChannelPinnedTopics#fe198602 flags:# channel_id:long order:flags.0?Vector<int> = Update;

inputReplyToMessage#869fbe10 flags:# reply_to_msg_id:int top_msg_id:flags.0?int reply_to_peer_id:flags.1?InputPeer quote_text:flags.2?string quote_entities:flags.3?Vector<MessageEntity> quote_offset:flags.4?int monoforum_peer_id:flags.5?InputPeer todo_item_id:flags.6?int = InputReplyTo;

---functions---

channels.getForumTopics#0de560d1 flags:# channel:InputChannel q:flags.0?string offset_date:int offset_id:int offset_topic:int limit:int = messages.ForumTopics;
channels.getForumTopicsByID#b0831eb9 channel:InputChannel topics:Vector<int> = messages.ForumTopics;

channels.deleteTopicHistory#34435f2d channel:InputChannel top_msg_id:int = messages.AffectedHistory;

channels.createForumTopic#f40c0224 flags:# channel:InputChannel title:string icon_color:flags.0?int icon_emoji_id:flags.3?long random_id:long send_as:flags.2?InputPeer = Updates;
channels.editForumTopic#f4dfa185 flags:# channel:InputChannel topic_id:int title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = Updates;

channels.updatePinnedForumTopic#6c2d9026 channel:InputChannel topic_id:int pinned:Bool = Updates;
channels.reorderPinnedForumTopics#2950a18f flags:# force:flags.0?true channel:InputChannel order:Vector<int> = Updates;

channels.toggleViewForumAsMessages#9738bb15 channel:InputChannel enabled:Bool = Updates;
```

Forums can have multiple topics where users may interact.

To fetch the topic list of a forum, use channels.getForumTopics; the same method can be used to search topics by their name.
To fetch information about one or more topics by their ID, use channels.getForumTopicsByID.

Every forum has a non-deletable "General" topic, with id=1; other topics will have other IDs, equal to the messageActionTopicCreate service message that created the topic.

To send messages to the "General" topic, just use messages.sendMessage as usual, as if you were writing to a normal supergroup.
On the other hand, topics with id != 1 are just the message thread of the messageActionTopicCreate service message that created that topic.
This means that topics should be treated similarly to message threads by the client.
To send messages to these topics, pass the topic ID to the reply_to_msg_id parameter of inputReplyToMessage, passed to reply_to when invoking messages.sendMessage, messages.sendMedia et cetera.

To reply to messages within a topic, pass the ID of the message to reply to inputReplyToMessage.reply_to_msg_id, and, unless we're replying to a message in the "General" topic, pass the topic ID to inputReplyToMessage.top_msg_id.
Note that when replying to messages in a topic, the inputReplyToMessage.top_msg_id field must contain the topic ID if and only if we're replying to messages in forum topics different from the "General" topic (i.e. reply_to_msg_id is set and reply_to_msg_id != topicID and topicID != 1): this way, if the replied-to message is deleted before the method finishes execution, the value in this field will be used to send the message to the correct topic, instead of the "General" topic.
Also note that since message threads can't have nested message threads, topics (except for the "General" topic) also can't have message threads (so replies to messages within topics won't generate further message threads).

Topics have a name (title) and an icon: the icon can be a custom emoji specified by the icon_emoji_id, or a default chat icon if icon_emoji_id is not set, filled with the color specified in icon_color.
Topics can be temporarily closed, preventing further messages from being sent to the topic.
Additionally, (only) the "General" topic may also be hidden.
All topics except for the "General" topic can be deleted by invoking channels.deleteTopicHistory, with the topic ID.

Topics can be created by using the channels.createForumTopic method, and may be modified with the channels.editForumTopic method: these actions require manage_topics rights, and will generate messageActionTopicCreate/messageActionTopicEdit service messages.

Note that Telegram Premium users can pass any custom emoji to icon_emoji_id, while other users can only use the custom emojis contained in the inputStickerSetEmojiDefaultTopicIcons emoji pack.
If the default chat icon is used, its color cannot be modified after creating the topic.

Topics may be pinned or unpinned using channels.updatePinnedForumTopic; use channels.reorderPinnedForumTopics to reorder pinned topics.
You can pin at most topics_pinned_limit topics per forum, as specified by the client configuration parameters ».

Users may also choose to display messages from all topics as if they were sent to a normal group, using a "View as messages" setting in the local client.
This setting only affects the current account, and is synced to other logged in sessions using the channels.toggleViewForumAsMessages method; invoking this method will update the value of the view_forum_as_messages flag of channelFull or dialog and emit an updateChannelViewForumAsMessages.

#### Tabbed or list-based forum UI

```
channel#fe685355 flags:# creator:flags.0?true left:flags.2?true broadcast:flags.5?true verified:flags.7?true megagroup:flags.8?true restricted:flags.9?true signatures:flags.11?true min:flags.12?true scam:flags.19?true has_link:flags.20?true has_geo:flags.21?true slowmode_enabled:flags.22?true call_active:flags.23?true call_not_empty:flags.24?true fake:flags.25?true gigagroup:flags.26?true noforwards:flags.27?true join_to_send:flags.28?true join_request:flags.29?true forum:flags.30?true flags2:# stories_hidden:flags2.1?true stories_hidden_min:flags2.2?true stories_unavailable:flags2.3?true signature_profiles:flags2.12?true autotranslation:flags2.15?true broadcast_messages_allowed:flags2.16?true monoforum:flags2.17?true forum_tabs:flags2.19?true id:long access_hash:flags.13?long title:string username:flags.6?string photo:ChatPhoto date:int restriction_reason:flags.9?Vector<RestrictionReason> admin_rights:flags.14?ChatAdminRights banned_rights:flags.15?ChatBannedRights default_banned_rights:flags.18?ChatBannedRights participants_count:flags.17?int usernames:flags2.0?Vector<Username> stories_max_id:flags2.4?int color:flags2.7?PeerColor profile_color:flags2.8?PeerColor emoji_status:flags2.9?EmojiStatus level:flags2.10?int subscription_until_date:flags2.11?int bot_verification_icon:flags2.13?long send_paid_messages_stars:flags2.14?long linked_monoforum_id:flags2.18?long = Chat;

---functions---

channels.toggleForum#3ff75734 channel:InputChannel enabled:Bool tabs:Bool = Updates;
```

Forums can use either a tabbed or list-based UI for topic selection, according to the value of the channel.forum_tabs flag.

This flag can be toggled using channels.toggleForum, by passing enabled=true and tabs=true|false to enable or disable the tabbed UI.

### Monoforums

Monoforums are a special kind of forum, used to implement direct messages to channels.

While in the API they are sometimes called "monoforums", they actually share more similarities with the saved messages API: see here » for the full documentation on direct channel messages.

