# Threads
Telegram allows commenting on a channel post or on a generic supergroup message, thanks to message threads.
### Message threads
Schema:
Threads are usually automatically created when replying to any message in a group.
For example, all replies to a message with ID 420 are associated to thread with ID 420, unique to this group; this thread ID is contained in the reply_to_top_id field of reply_to messageReplyHeader, along with an eventual reply_to_msg_id, for replies to messages within a thread.
Replies to messages in a thread are part of the same thread, and do not spawn new threads.
When receiving a message from a group that is also the top of a thread (the message with ID 420), the replies optional field will contain a messageReplies constructor, containing the message ID and PTS of the latest reply in the thread, and the message ID of the latest read thread reply, along with the total number of replies in the thread.
Replies to a thread can also be manually fetched using messages.search, providing to top_msg_id the thread ID.
### Channel comments
The same messageReplies constructor seen above will also be contained in channel posts, this time containing information about the comment section of a specific channel post, see here » for more info.
