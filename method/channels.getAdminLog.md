# channels.getAdminLog
Get the admin log of a channel/supergroup

```
channels.adminLogResults#ed8af74d events:Vector<ChannelAdminLogEvent> chats:Vector<Chat> users:Vector<User> = channels.AdminLogResults;
---functions---
channels.getAdminLog#33ddf480 flags:# channel:InputChannel q:string events_filter:flags.0?ChannelAdminLogEventsFilter admins:flags.1?Vector<InputUser> max_id:long min_id:long limit:int = channels.AdminLogResults;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel | InputChannel | Channel |
| q | string | Search query, can be empty |
| events_filter | flags.0?ChannelAdminLogEventsFilter | Event filter |
| admins | flags.1?Vector<InputUser> | Only show events from these admins |
| max_id | long | Maximum ID of message to return (see pagination) |
| min_id | long | Minimum ID of message to return (see pagination) |
| limit | int | Maximum number of results to return, see pagination |


## Result
channels.AdminLogResults

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 406 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 403 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |

