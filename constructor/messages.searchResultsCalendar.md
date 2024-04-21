# messages.searchResultsCalendar
Information about found messages sent on a specific day

```
messages.searchResultsCalendar#147ee23c flags:# inexact:flags.0?true count:int min_date:int min_msg_id:int offset_id_offset:flags.1?int periods:Vector<SearchResultsCalendarPeriod> messages:Vector<Message> chats:Vector<Chat> users:Vector<User> = messages.SearchResultsCalendar;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| inexact | flags.0?true | If set, indicates that the results may be inexact |
| count | int | Total number of results matching query |
| min_date | int | Starting timestamp of attached messages |
| min_msg_id | int | Ending timestamp of attached messages |
| offset_id_offset | flags.1?int | Indicates the absolute position of messages[0] within the total result set with count count. This is useful, for example, if we need to display a progress/total counter (like photo 134 of 200, for all media in a chat, we could simply use photo ${offset_id_offset} of ${count}. |
| periods | Vector<SearchResultsCalendarPeriod> | Used to split the messages by days: multiple SearchResultsCalendarPeriod constructors are returned, each containing information about the first, last and total number of messages matching the filter that were sent on a specific day.  This information can be easily used to split the returned messages by day. |
| messages | Vector<Message> | Messages |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |


## Type
messages.SearchResultsCalendar

## Related pages
