# Discussion groups

Groups can be associated to a channel as a discussion group, to allow users to discuss about posts.

### Channel comments

A discussion group can be associated to a channel using channels.setDiscussionGroup.
The discussion group can be accessed in the client by clicking on the discuss button of the channel, or by accessing the comment section of a specific post; the discussion group ID is also present in the linked_chat_id field of the channelFull constructor.

All messages sent to the channel will also be forwarded to the linked group (with sender peer from_id equal to the peer of the linked channel); those messages will also be automatically pinned in the group.

The comment section of a channel post is simply the message thread of the automatically forwarded channel message in the linked discussion supergroup.
Thus, the comment section of a particular post can be disabled by removing the autoforwarded channel post message from the discussion group.

A messageReplies constructor will be attached the channel post in the original channel, containing information about the comment section, specifically:

- replies.channel_id will contain the ID of the linked discussion supergroup

- replies.recent_repliers will contain information about the last few comment posters for a specific thread, to show a small list of commenter profile pictures in client previews.

- replies.replies will contains the total number of replies in the comment section.

- replies.max_id may contain the ID of the latest message in the comment section, if any.

- replies.replies_pts may contain the PTS of the autoforwarded channel message that started the comment section.

The same messageReplies constructor with the usual flags for a thread (i.e. without channel_id, recent_replies) will also be present in the message automatically forwarded to the discussion group, as for all group messages that start a thread.

Use messages.getDiscussionMessage to obtain the initial messages of the message thread of the autoforwaded channel message in the linked discussion supergroup.

The messages are returned in a reverse chronological order (i.e., in order of decreasing message ID); thus the last message returned by the method will be the autoforwarded channel message that started the comment section.

#### @replies

Since a user can comment in channel posts without joining the actual discussion supergroup, there must be a way for them to receive notifications about replies in comment sections.
For this reason, a special @replies username is provided.
Its ID for main and testing endpoints can be seen in the tdlib sources.

When someone replies to one of our messages in the comment section of a channel post, and the user is not subscribed to the discussion group, the client will receive two updates:

- An updateNewChannelMessage from the discussion group itself, structured just like any other update coming from a subscribed group, with:

- id set to the ID of the reply

- from_id set to the peer that replied to us

- peer_id set to the peer of the discussion group

- reply_to.reply_to_msg_id set to the ID of our message

- reply_to.reply_to_top_id set to the thread ID.

- An updateNewMessage

- id set to the common ID sequence for users

- from_id set to the peer of @replies

- peer_id set to our own peer

- fwd_from.saved_from_msg_id set to the ID of the reply

- fwd_from.from_id set to the peer that replied to us

- reply_to.reply_to_peer_id set to the peer of the discussion group

- reply_to.reply_to_msg_id set to the ID of our message

- reply_to.reply_to_top_id set to the thread ID

Clients should display messages coming from @replies as a read-only supergroup, with each reply displayed as a separate message from the author of the reply, with a "View in chat" button like for channel comments.

contacts.blockFromReplies may be used to stop getting notifications about thread replies from a certain user in @replies.

### Linking a discussion group

To obtain a list of admined supergroups that a channel admin can possibly associate to a channel, use channels.getGroupsForDiscussion.
Returned basic group chats must be first upgraded to supergroups before they can be set as a discussion group.
Before linking a supergroup to a channel, access to the supergroup's old messages must also be enabled using channels.togglePreHistoryHidden.

To set a returned supergroup as a discussion group use channels.setDiscussionGroup.

Schema:

### Requiring users to join the group

Admins may use channels.toggleJoinToSend to force users to join a discussion group before commenting.
The channel.join_to_send flag will be set accordingly, and all attempts by non-members to send a message to the group will return a CHAT_GUEST_SEND_FORBIDDEN RPC error.

