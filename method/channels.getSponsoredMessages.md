# channels.getSponsoredMessages
Get a list of sponsored messages

```
messages.sponsoredMessages#c9ee1d87 flags:# posts_between:flags.0?int messages:Vector<SponsoredMessage> chats:Vector<Chat> users:Vector<User> = messages.SponsoredMessages;
messages.sponsoredMessagesEmpty#1839490f = messages.SponsoredMessages;
---functions---
channels.getSponsoredMessages#ec210fbf channel:InputChannel = messages.SponsoredMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| channel | InputChannel | Peer |


## Result
messages.SponsoredMessages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |

