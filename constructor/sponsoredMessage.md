# sponsoredMessage
A sponsored message.

```
sponsoredMessage#ed5383f7 flags:# recommended:flags.5?true show_peer_photo:flags.6?true random_id:bytes from_id:flags.3?Peer chat_invite:flags.4?ChatInvite chat_invite_hash:flags.4?string channel_post:flags.2?int start_param:flags.0?string webpage:flags.9?SponsoredWebPage app:flags.10?BotApp message:string entities:flags.1?Vector<MessageEntity> button_text:flags.11?string sponsor_info:flags.7?string additional_info:flags.8?string = SponsoredMessage;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| recommended | flags.5?true | Whether the message needs to be labeled as "recommended" instead of "sponsored" |
| show_peer_photo | flags.6?true | Whether a profile photo bubble should be displayed for this message, like for messages sent in groups. The photo shown in the bubble is obtained either from the peer contained in from_id, or from chat_invite. |
| random_id | bytes | Message ID |
| from_id | flags.3?Peer | ID of the sender of the message |
| chat_invite | flags.4?ChatInvite | Information about the chat invite hash specified in chat_invite_hash |
| chat_invite_hash | flags.4?string | Chat invite |
| channel_post | flags.2?int | Optional link to a channel post if from_id points to a channel |
| start_param | flags.0?string | Parameter for the bot start message if the sponsored chat is a chat with a bot. |
| webpage | flags.9?SponsoredWebPage | Sponsored website |
| app | flags.10?BotApp | Mini App » to open when the sponsored message is clicked. |
| message | string | Sponsored message |
| entities | flags.1?Vector<MessageEntity> | Message entities for styled text |
| button_text | flags.11?string | Text of the sponsored message button. |
| sponsor_info | flags.7?string | If set, contains additional information about the sponsor to be shown along with the message. |
| additional_info | flags.8?string | If set, contains additional information about the sponsored message to be shown along with the message. |


## Type
SponsoredMessage

## Related pages
