# messages.getSearchResultsPositions
Returns sparse positions of messages of the specified type in the chat to be used for shared media scroll implementation.

```
messages.searchResultsPositions#53b22baf count:int positions:Vector<SearchResultsPosition> = messages.SearchResultsPositions;
---functions---
messages.getSearchResultsPositions#9c7f2f10 flags:# peer:InputPeer saved_peer_id:flags.2?InputPeer filter:MessagesFilter offset_id:int limit:int = messages.SearchResultsPositions;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | Peer where to search |
| saved_peer_id | flags.2?InputPeer | Search within the saved message dialog » with this ID. |
| filter | MessagesFilter | Message filter, inputMessagesFilterEmpty, inputMessagesFilterMyMentions filters are not supported by this method. |
| offset_id | int | Offsets for pagination, for more info click here |
| limit | int | Maximum number of results to return, see pagination |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

