# channels.getLeftChannels
Get a list of channels/supergroups we left, requires a takeout session, see here » for more info.

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;
---functions---
channels.getLeftChannels#8341ecc0 offset:int = messages.Chats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| offset | int | Offset for pagination |


## Result
messages.Chats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | TAKEOUT_REQUIRED | A takeout session needs to be initialized first, see here » for more info. |

