# account.initTakeoutSession
Initialize a takeout session, see here » for more info.

```
account.takeout#4dba4501 id:long = account.Takeout;
---functions---
account.initTakeoutSession#8ef3eab0 flags:# contacts:flags.0?true message_users:flags.1?true message_chats:flags.2?true message_megagroups:flags.3?true message_channels:flags.4?true files:flags.5?true file_max_size:flags.5?long = account.Takeout;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| contacts | flags.0?true | Whether to export contacts |
| message_users | flags.1?true | Whether to export messages in private chats |
| message_chats | flags.2?true | Whether to export messages in basic groups |
| message_megagroups | flags.3?true | Whether to export messages in supergroups |
| message_channels | flags.4?true | Whether to export messages in channels |
| files | flags.5?true | Whether to export files |
| file_max_size | flags.5?long | Maximum size of files to export |


## Result
account.Takeout

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 420 | TAKEOUT_INIT_DELAY_%d | Sorry, for security reasons, you will be able to begin downloading your data in %d seconds. We have notified all your devices about the export request to make sure it's authorized and to give you time to react if it's not. |

