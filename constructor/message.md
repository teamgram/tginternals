# message
A message

```
message#76bec211 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true from_scheduled:flags.18?true legacy:flags.19?true edit_hide:flags.21?true pinned:flags.24?true noforwards:flags.26?true invert_media:flags.27?true id:int from_id:flags.8?Peer peer_id:Peer saved_peer_id:flags.28?Peer fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader date:int message:string media:flags.9?MessageMedia reply_markup:flags.6?ReplyMarkup entities:flags.7?Vector<MessageEntity> views:flags.10?int forwards:flags.10?int replies:flags.23?MessageReplies edit_date:flags.15?int post_author:flags.16?string grouped_id:flags.17?long reactions:flags.20?MessageReactions restriction_reason:flags.22?Vector<RestrictionReason> ttl_period:flags.25?int = Message;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| out | flags.1?true | Is this an outgoing message |
| mentioned | flags.4?true | Whether we were mentioned in this message |
| media_unread | flags.5?true | Whether there are unread media attachments in this message |
| silent | flags.13?true | Whether this is a silent message (no notification triggered) |
| post | flags.14?true | Whether this is a channel post |
| from_scheduled | flags.18?true | Whether this is a scheduled message |
| legacy | flags.19?true | This is a legacy message: it has to be refetched with the new layer |
| edit_hide | flags.21?true | Whether the message should be shown as not modified to the user, even if an edit date is present |
| pinned | flags.24?true | Whether this message is pinned |
| noforwards | flags.26?true | Whether this message is protected and thus cannot be forwarded; clients should also prevent users from saving attached media (i.e. videos should only be streamed, photos should be kept in RAM, et cetera). |
| invert_media | flags.27?true | If set, any eventual webpage preview will be shown on top of the message instead of at the bottom. |
| id | int | ID of the message |
| from_id | flags.8?Peer | ID of the sender of the message |
| peer_id | Peer | Peer ID, the chat where this message was sent |
| saved_peer_id | flags.28?Peer | Messages fetched from a saved messages dialog » will have peer=inputPeerSelf and the saved_peer_id flag set to the ID of the saved dialog. |
| fwd_from | flags.2?MessageFwdHeader | Info about forwarded messages |
| via_bot_id | flags.11?long | ID of the inline bot that generated the message |
| reply_to | flags.3?MessageReplyHeader | Reply information |
| date | int | Date of the message |
| message | string | The message |
| media | flags.9?MessageMedia | Media attachment |
| reply_markup | flags.6?ReplyMarkup | Reply markup (bot/inline keyboards) |
| entities | flags.7?Vector<MessageEntity> | Message entities for styled text |
| views | flags.10?int | View count for channel posts |
| forwards | flags.10?int | Forward counter |
| replies | flags.23?MessageReplies | Info about post comments (for channels) or message replies (for groups) |
| edit_date | flags.15?int | Last edit date of this message |
| post_author | flags.16?string | Name of the author of this message for channel posts (with signatures enabled) |
| grouped_id | flags.17?long | Multiple media messages sent using messages.sendMultiMedia with the same grouped ID indicate an album or media group |
| reactions | flags.20?MessageReactions | Reactions to this message |
| restriction_reason | flags.22?Vector<RestrictionReason> | Contains the reason why access to this message must be restricted. |
| ttl_period | flags.25?int | Time To Live of the message, once message.date+message.ttl_period === time(), the message will be deleted on the server, and must be deleted locally as well. |


## Type
Message

## Related pages
