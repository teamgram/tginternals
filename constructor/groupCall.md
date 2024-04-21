# groupCall
Info about a group call or livestream

```
groupCall#d597650c flags:# join_muted:flags.1?true can_change_join_muted:flags.2?true join_date_asc:flags.6?true schedule_start_subscribed:flags.8?true can_start_video:flags.9?true record_video_active:flags.11?true rtmp_stream:flags.12?true listeners_hidden:flags.13?true id:long access_hash:long participants_count:int title:flags.3?string stream_dc_id:flags.4?int record_start_date:flags.5?int schedule_date:flags.7?int unmuted_video_count:flags.10?int unmuted_video_limit:int version:int = GroupCall;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| join_muted | flags.1?true | Whether the user should be muted upon joining the call |
| can_change_join_muted | flags.2?true | Whether the current user can change the value of the join_muted flag using phone.toggleGroupCallSettings |
| join_date_asc | flags.6?true | Specifies the ordering to use when locally sorting by date and displaying in the UI group call participants. |
| schedule_start_subscribed | flags.8?true | Whether we subscribed to the scheduled call |
| can_start_video | flags.9?true | Whether you can start streaming video into the call |
| record_video_active | flags.11?true | Whether the group call is currently being recorded |
| rtmp_stream | flags.12?true | Whether RTMP streams are allowed |
| listeners_hidden | flags.13?true | Whether the listeners list is hidden and cannot be fetched using phone.getGroupParticipants. The phone.groupParticipants.count and groupCall.participants_count counters will still include listeners. |
| id | long | Group call ID |
| access_hash | long | Group call access hash |
| participants_count | int | Participant count |
| title | flags.3?string | Group call title |
| stream_dc_id | flags.4?int | DC ID to be used for livestream chunks |
| record_start_date | flags.5?int | When was the recording started |
| schedule_date | flags.7?int | When is the call scheduled to start |
| unmuted_video_count | flags.10?int | Number of people currently streaming video into the call |
| unmuted_video_limit | int | Maximum number of people allowed to stream video into the call |
| version | int | Version |


## Type
GroupCall

## Related pages
