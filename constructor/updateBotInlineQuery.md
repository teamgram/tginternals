# updateBotInlineQuery
An incoming inline query

```
updateBotInlineQuery#496f379c flags:# query_id:long user_id:long query:string geo:flags.0?GeoPoint peer_type:flags.1?InlineQueryPeerType offset:string = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query_id | long | Query ID |
| user_id | long | User that sent the query |
| query | string | Text of query |
| geo | flags.0?GeoPoint | Attached geolocation |
| peer_type | flags.1?InlineQueryPeerType | Type of the chat from which the inline query was sent. |
| offset | string | Offset to navigate through results |


## Type
Update

## Related pages
