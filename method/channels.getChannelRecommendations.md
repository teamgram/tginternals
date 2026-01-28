# channels.getChannelRecommendations
Obtain a list of similarly themed public channels, selected based on similarities in their subscriber bases.

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;
---functions---
channels.getChannelRecommendations#25a71742 flags:# channel:flags.0?InputChannel = messages.Chats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| channel | flags.0?InputChannel | The method will return channels related to the passed channel. If not set, the method will returns channels related to channels the user has joined. |


## Result
messages.Chats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | CHAT_NOT_MODIFIED | No changes were made to chat information because the new information you passed is identical to the current information. |

