# channels.setDiscussionGroup
Associate a group to a channel as discussion group for that channel

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
channels.setDiscussionGroup#40582bb2 broadcast:InputChannel group:InputChannel = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| broadcast | InputChannel | Channel |
| group | InputChannel | Discussion group to associate to the channel |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BROADCAST_ID_INVALID | Broadcast ID invalid. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHAT_ADMIN_REQUIRED | You must be an admin in this chat to do this. |
| 403 | CHAT_WRITE_FORBIDDEN | You can't write in this chat. |
| 400 | LINK_NOT_MODIFIED | Discussion link not modified. |
| 400 | MEGAGROUP_ID_INVALID | Invalid supergroup ID. |
| 400 | MEGAGROUP_PREHISTORY_HIDDEN | Group with hidden history for new members can't be set as discussion groups. |

