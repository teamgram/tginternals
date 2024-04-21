# channels.getChannelRecommendations
Obtain a list of similarly themed public channels, selected based on similarities in their subscriber bases.

```
messages.chats#64ff9fd5 chats:Vector<Chat> = messages.Chats;
messages.chatsSlice#9cd81144 count:int chats:Vector<Chat> = messages.Chats;
---functions---
channels.getChannelRecommendations#83b70d97 channel:InputChannel = messages.Chats;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | The method will return channels related to the passed channel. |


## Result
messages.Chats

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |

