# Forums

Telegram allows creating forums with multiple distinct topics.

Forums may be created either by invoking channels.createChannel with the forum flag set, or by converting an existing supergroup into a forum using channels.toggleForum with enabled=true.
If the group is a basic group, it should be upgraded to a supergroup before converting it into a forum.

Forums can also be converted back to supergroups using channels.toggleForum with enabled=false.

Note that the channels.toggleForum method can only be invoked by admins with owner rights.

Forums have the channel.forum flag set, and conversation happens in distinct forum topics.

#### Forum topics

Forums can have multiple topics where users may interact.

To fetch the topic list of a forum, use channels.getForumTopics; the same method can be used to search topics by their name.
To fetch information about one or more topics by their ID, use channels.getForumTopicsByID.

Every forum has a non-deletable "General" topic, with id=1; other topics will have other IDs, equal to the messageActionTopicCreate service message that created the topic.

To send messages to the "General" topic, just use messages.sendMessage as usual, as if you were writing to a normal supergroup.
On the other hand, topics with id != 1 are just the message thread of the messageActionTopicCreate service message that created that topic.
This means that topics should be treated similarly to message threads by the client.
To send messages to these topics, pass the topic ID to the reply_to_msg_id parameter of inputReplyToMessage, passed to reply_to when invoking messages.sendMessage, messages.sendMedia et cetera.

To reply to messages within a topic, pass the ID of the message to reply to to inputReplyToMessage.reply_to_msg_id, and, unless we're replying to a message in the "General" topic, pass the topic ID to inputReplyToMessage.top_msg_id.
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
You can pin at most topics_pinned_limit topics per forum, as specified by the client configuration parameters ».

Users may also choose to display messages from all topics as if they were sent to a normal group, using a "View as messages" setting in the local client.
This setting only affects the current account, and is synced to other logged in sessions using the channels.toggleViewForumAsMessages method; invoking this method will update the value of the view_forum_as_messages flag of channelFull or dialog and emit an updateChannelViewForumAsMessages.

