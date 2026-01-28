# messages.getSponsoredMessages
Get a list of sponsored messages for a peer, see here » for more info.

```
messages.sponsoredMessages#ffda656d flags:# posts_between:flags.0?int start_delay:flags.1?int between_delay:flags.2?int messages:Vector<SponsoredMessage> chats:Vector<Chat> users:Vector<User> = messages.SponsoredMessages;
messages.sponsoredMessagesEmpty#1839490f = messages.SponsoredMessages;
---functions---
messages.getSponsoredMessages#3d6ce850 flags:# peer:InputPeer msg_id:flags.0?int = messages.SponsoredMessages;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| peer | InputPeer | The currently open channel/bot. |
| msg_id | flags.0?int | Must be set when fetching sponsored messages to show on channel videos ». |


## Result
messages.SponsoredMessages

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |

