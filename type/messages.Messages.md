# messages.Messages
Object contains information on list of messages with auxiliary data.

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#762b263d flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int search_flood:flags.3?SearchPostsFlood messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;

---functions---

messages.getMessages#63c66506 id:Vector<InputMessage> = messages.Messages;
messages.getHistory#4423e6c5 peer:InputPeer offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
messages.search#29ee847a flags:# peer:InputPeer q:string from_id:flags.0?InputPeer saved_peer_id:flags.2?InputPeer saved_reaction:flags.3?Vector<Reaction> top_msg_id:flags.1?int filter:MessagesFilter min_date:int max_date:int offset_id:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
messages.searchGlobal#4bc6589a flags:# broadcasts_only:flags.1?true groups_only:flags.2?true users_only:flags.3?true folder_id:flags.0?int q:string filter:MessagesFilter min_date:int max_date:int offset_rate:int offset_peer:InputPeer offset_id:int limit:int = messages.Messages;
messages.getUnreadMentions#f107e790 flags:# peer:InputPeer top_msg_id:flags.0?int offset_id:int add_offset:int limit:int max_id:int min_id:int = messages.Messages;
messages.getRecentLocations#702a40e0 peer:InputPeer limit:int hash:long = messages.Messages;
messages.getScheduledHistory#f516760b peer:InputPeer hash:long = messages.Messages;
messages.getScheduledMessages#bdbb0464 peer:InputPeer id:Vector<int> = messages.Messages;
messages.getReplies#22ddd30c peer:InputPeer msg_id:int offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
messages.getUnreadReactions#bd7f90ac flags:# peer:InputPeer top_msg_id:flags.0?int saved_peer_id:flags.1?InputPeer offset_id:int add_offset:int limit:int max_id:int min_id:int = messages.Messages;
messages.searchSentMedia#107e31a0 q:string filter:MessagesFilter limit:int = messages.Messages;
messages.getSavedHistory#998ab009 flags:# parent_peer:flags.0?InputPeer peer:InputPeer offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
messages.getQuickReplyMessages#94a495c3 flags:# shortcut_id:int id:flags.0?Vector<int> hash:long = messages.Messages;

channels.getMessages#ad8c9a23 channel:InputChannel id:Vector<InputMessage> = messages.Messages;
channels.searchPosts#f2c4f24d flags:# hashtag:flags.0?string query:flags.1?string offset_rate:int offset_peer:InputPeer offset_id:int limit:int allow_paid_stars:flags.2?long = messages.Messages;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.messages | Full list of messages with auxiliary data. |
| messages.messagesSlice | Incomplete list of messages and auxiliary data. |
| messages.channelMessages | Channel messages |
| messages.messagesNotModified | No new messages matching the query were found |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getMessages | Returns the list of messages by their IDs. |
| messages.getHistory | Returns the conversation history with one interlocutor / within a chat |
| messages.search | Search for messages. |
| messages.searchGlobal | Search for messages and peers globally |
| messages.getUnreadMentions | Get unread messages where we were mentioned |
| messages.getRecentLocations | Get live location history of a certain user |
| messages.getScheduledHistory | Get scheduled messages |
| messages.getScheduledMessages | Get scheduled messages |
| messages.getReplies | Get messages in a reply thread |
| messages.getUnreadReactions | Get unread reactions to messages you sent |
| messages.searchSentMedia | View and search recently sent media.  This method does not support pagination. |
| messages.getSavedHistory | Fetch saved messages » forwarded from a specific peer, or fetch messages from a monoforum topic ». |
| messages.getQuickReplyMessages | Fetch (a subset or all) messages in a quick reply shortcut ». |
| channels.getMessages | Get channel/supergroup messages |
| channels.searchPosts | Globally search for posts from public channels » (including those we aren't a member of) containing either a specific hashtag, or a full text query.Exactly one of query and hashtag must be set. |


