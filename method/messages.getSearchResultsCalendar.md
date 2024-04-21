# messages.getSearchResultsCalendar
Returns information about the next messages of the specified type in the chat split by days.

```
messages.searchResultsCalendar#147ee23c flags:# inexact:flags.0?true count:int min_date:int min_msg_id:int offset_id_offset:flags.1?int periods:Vector<SearchResultsCalendarPeriod> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SearchResultsCalendar;
---functions---
messages.getSearchResultsCalendar#6aa3f6bd flags:# peer:InputPeer saved_peer_id:flags.2?InputPeer filter:MessagesFilter offset_id:int offset_date:int = messages.SearchResultsCalendar;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer where to search |
| saved_peer_id | flags.2?InputPeer | Search within the saved message dialog » with this ID. |
| filter | MessagesFilter | Message filter, inputMessagesFilterEmpty, inputMessagesFilterMyMentions filters are not supported by this method. |
| offset_id | int | Offsets for pagination, for more info click here |
| offset_date | int | Offsets for pagination, for more info click here |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | FILTER_NOT_SUPPORTED | The specified filter cannot be used in this context. |

