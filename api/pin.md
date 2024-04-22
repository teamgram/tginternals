# Pinned messages

Telegram allows pinning multiple messages on top of a specific chat.

The messages.updatePinnedMessage method can be used to pin or unpin a specific message in an arbitrary chat.
The unpin flags specifies whether to unpin or pin the message, and pm_oneside specifies whether the message should only be pinned on the local side of a one-to-one chat.

messages.unpinAllMessages can be used to unpin all messages in a chat.

When (un)pinning messages, a updatePinnedMessages or updatePinnedChannelMessages update will be emitted, containing IDs of pinned or unpinned messages.

Pinned messages will also have the will also have the pinned flag of message set.

### Getting pinned messages

The pinned_msg_id of userFull, chatFull, channelFull contains the ID of only the latest pinned message.
To obtain a full list, use messages.search with inputMessagesFilterPinned filter.

