# message
A message

```
message#9815cec8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true from_scheduled:flags.18?true legacy:flags.19?true edit_hide:flags.21?true pinned:flags.24?true noforwards:flags.26?true invert_media:flags.27?true flags2:# offline:flags2.1?true video_processing_pending:flags2.4?true paid_suggested_post_stars:flags2.8?true paid_suggested_post_ton:flags2.9?true id:int from_id:flags.8?Peer from_boosts_applied:flags.29?int peer_id:Peer saved_peer_id:flags.28?Peer fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long via_business_bot_id:flags2.0?long reply_to:flags.3?MessageReplyHeader date:int message:string media:flags.9?MessageMedia reply_markup:flags.6?ReplyMarkup entities:flags.7?Vector<MessageEntity> views:flags.10?int forwards:flags.10?int replies:flags.23?MessageReplies edit_date:flags.15?int post_author:flags.16?string grouped_id:flags.17?long reactions:flags.20?MessageReactions restriction_reason:flags.22?Vector<RestrictionReason> ttl_period:flags.25?int quick_reply_shortcut_id:flags.30?int effect:flags2.2?long factcheck:flags2.3?FactCheck report_delivery_until_date:flags2.5?int paid_message_stars:flags2.6?long suggested_post:flags2.7?SuggestedPost = Message;
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
| flags2 | # | Flags, see TL conditional fields |
| offline | flags2.1?true | If set, the message was sent because of a scheduled action by the message sender, for example, as away, or a greeting service message. |
| video_processing_pending | flags2.4?true | The video contained in the message is currently being processed by the server (i.e. to generate alternative qualities, that will be contained in the final messageMediaDocument.alt_document), and will be sent once the video is processed, which will happen approximately at the specified date (i.e. messages with this flag set should be treated similarly to scheduled messages, but instead of the scheduled date, date contains the estimated conversion date). See here » for more info. |
| paid_suggested_post_stars | flags2.8?true | Set if this is a suggested channel post » that was paid using Telegram Stars. |
| paid_suggested_post_ton | flags2.9?true | Set if this is a suggested channel post » that was paid using Toncoins. |
| id | int | ID of the message |
| from_id | flags.8?Peer | ID of the sender of the message |
| from_boosts_applied | flags.29?int | Supergroups only, contains the number of boosts this user has given the current supergroup, and should be shown in the UI in the header of the message. Only present for incoming messages from non-anonymous supergroup members that have boosted the supergroup. Note that this counter should be locally overridden for non-anonymous outgoing messages, according to the current value of channelFull.boosts_applied, to ensure the value is correct even for messages sent by the current user before a supergroup was boosted (or after a boost has expired or the number of boosts has changed); do not update this value for incoming messages from other users, even if their boosts have changed. |
| peer_id | Peer | Peer ID, the chat where this message was sent |
| saved_peer_id | flags.28?Peer | Messages from a saved messages dialog » will have peer=inputPeerSelf and the saved_peer_id flag set to the ID of the saved dialog.Messages from a monoforum » will have peer=ID of the monoforum and the saved_peer_id flag set to the ID of a topic. |
| fwd_from | flags.2?MessageFwdHeader | Info about forwarded messages |
| via_bot_id | flags.11?long | ID of the inline bot that generated the message |
| via_business_bot_id | flags2.0?long | Whether the message was sent by the business bot specified in via_bot_id on behalf of the user. |
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
| quick_reply_shortcut_id | flags.30?int | If set, this message is a quick reply shortcut message » (note that quick reply shortcut messages sent to a private chat will not have this field set). |
| effect | flags2.2?long | A message effect that should be played as specified here ». |
| factcheck | flags2.3?FactCheck | Represents a fact-check ». |
| report_delivery_until_date | flags2.5?int | Used for Telegram Gateway verification messages: if set and the current unixtime is bigger than the specified unixtime, invoke messages.reportMessagesDelivery passing the ID and the peer of this message as soon as it is received by the client (optionally batching requests for the same peer). |
| paid_message_stars | flags2.6?long | The amount of stars the sender has paid to send the message, see here » for more info. |
| suggested_post | flags2.7?SuggestedPost | Used to suggest a post to a channel, see here » for more info on the full flow. |


## Type
Message

## Related pages
