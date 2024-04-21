# messages.Messages
Object contains information on list of messages with auxiliary data.

```
messages.messages#8c718e87 messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesSlice#3a54685e flags:# inexact:flags.1?true count:int next_rate:flags.0?int offset_id_offset:flags.2?int messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.channelMessages#c776ba4e flags:# inexact:flags.1?true pts:int count:int offset_id_offset:flags.2?int messages:Vector<Message> topics:Vector<ForumTopic> chats:Vector<Chat> users:Vector<User> = messages.Messages;
messages.messagesNotModified#74535f21 count:int = messages.Messages;

---functions---

messages.getMessages#63c66506 id:Vector<InputMessage> = messages.Messages;
messages.getHistory#4423e6c5 peer:InputPeer offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
messages.search#a7b4e929 flags:# peer:InputPeer q:string from_id:flags.0?InputPeer saved_peer_id:flags.2?InputPeer top_msg_id:flags.1?int filter:MessagesFilter min_date:int max_date:int offset_id:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
messages.searchGlobal#4bc6589a flags:# broadcasts_only:flags.1?true folder_id:flags.0?int q:string filter:MessagesFilter min_date:int max_date:int offset_rate:int offset_peer:InputPeer offset_id:int limit:int = messages.Messages;
messages.getUnreadMentions#f107e790 flags:# peer:InputPeer top_msg_id:flags.0?int offset_id:int add_offset:int limit:int max_id:int min_id:int = messages.Messages;
messages.getRecentLocations#702a40e0 peer:InputPeer limit:int hash:long = messages.Messages;
messages.getScheduledHistory#f516760b peer:InputPeer hash:long = messages.Messages;
messages.getScheduledMessages#bdbb0464 peer:InputPeer id:Vector<int> = messages.Messages;
messages.getReplies#22ddd30c peer:InputPeer msg_id:int offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;
messages.getUnreadReactions#3223495b flags:# peer:InputPeer top_msg_id:flags.0?int offset_id:int add_offset:int limit:int max_id:int min_id:int = messages.Messages;
messages.searchSentMedia#107e31a0 q:string filter:MessagesFilter limit:int = messages.Messages;
messages.getSavedHistory#3d9a414d peer:InputPeer offset_id:int offset_date:int add_offset:int limit:int max_id:int min_id:int hash:long = messages.Messages;

channels.getMessages#ad8c9a23 channel:InputChannel id:Vector<InputMessage> = messages.Messages;
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
| channels.getMessages | Get channel/supergroup messages |
| messages.searchGlobal | Search for messages and peers globally |
| messages.getUnreadMentions | Get unread messages where we were mentioned |
| messages.getRecentLocations | Get live location history of a certain user |
| messages.getScheduledHistory | Get scheduled messages |
| messages.getScheduledMessages | Get scheduled messages |
| messages.getReplies | Get messages in a reply thread |
| messages.getUnreadReactions | Get unread reactions to messages you sent |
| messages.searchSentMedia | View and search recently sent media.  This method does not support pagination. |
| messages.getSavedHistory | Returns saved messages » forwarded from a specific peer |


