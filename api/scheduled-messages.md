# Scheduled messages

Telegram allows scheduling messages.

```
message#9815cec8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true from_scheduled:flags.18?true legacy:flags.19?true edit_hide:flags.21?true pinned:flags.24?true noforwards:flags.26?true invert_media:flags.27?true flags2:# offline:flags2.1?true video_processing_pending:flags2.4?true paid_suggested_post_stars:flags2.8?true paid_suggested_post_ton:flags2.9?true id:int from_id:flags.8?Peer from_boosts_applied:flags.29?int peer_id:Peer saved_peer_id:flags.28?Peer fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long via_business_bot_id:flags2.0?long reply_to:flags.3?MessageReplyHeader date:int message:string media:flags.9?MessageMedia reply_markup:flags.6?ReplyMarkup entities:flags.7?Vector<MessageEntity> views:flags.10?int forwards:flags.10?int replies:flags.23?MessageReplies edit_date:flags.15?int post_author:flags.16?string grouped_id:flags.17?long reactions:flags.20?MessageReactions restriction_reason:flags.22?Vector<RestrictionReason> ttl_period:flags.25?int quick_reply_shortcut_id:flags.30?int effect:flags2.2?long factcheck:flags2.3?FactCheck report_delivery_until_date:flags2.5?int paid_message_stars:flags2.6?long suggested_post:flags2.7?SuggestedPost = Message;

updateNewScheduledMessage#39a51dfb message:Message = Update;
updateDeleteScheduledMessages#f2a71983 flags:# peer:Peer messages:Vector<int> sent_messages:flags.0?Vector<int> = Update;

---functions---

messages.sendMessage#fe05dc9a flags:# no_webpage:flags.1?true silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;

messages.sendMedia#ac55d9c1 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
```

To schedule a message, simply provide a future unixtime in the schedule_date flag of messages.sendMessage or messages.sendMedia.

The specified message or media will be added to a server-side schedule queue for the current chat, and will be automatically sent at the specified time.
The method call generates the following updates:

- Immediately, an updateNewScheduledMessage, containing a message with ID equal to the ID of the message in the schedule queue for the current chat (each PM, chat, supergroup and channel has its own schedule queue and ID sequence), and date equal to schedule_date.

- At schedule_date, an updateNewMessage or updateNewChannelMessage with the from_scheduled flag set, indicating to the sender that the specified scheduled message was sent.

- At schedule_date, an updateDeleteScheduledMessages, indicating that the message was flushed from the schedule queue.

- The messages field will contain the scheduled message IDs for the sent messages (initially returned in updateNewScheduledMessage), and sent_messages will contain the real message IDs for the sent messages.

- The scheduled and real message ID for a given message will be at the same vector index, in messages and sent_messages respectively.

If the schedule_date is less than 10 seconds in the future, the message will be sent immediately, generating a normal updateNewMessage/updateNewChannelMessage.

Note: sending even non-scheduled videos to big channels will automatically trigger server-side processing (i.e. to generate alternative qualities, that will be contained in the final messageMediaDocument.alt_document).

These messages aren't sent immediately, and are instead added to the schedule queue similarly to scheduled messages, with a few differences:

- Immediately, an updateNewScheduledMessage, containing a message with ID equal to the ID of the message in the schedule queue for the current chat (each PM, chat, supergroup and channel has its own schedule queue and ID sequence), the video_processing_pending flag set and date equal to the estimated conversion date (not the schedule date).

- Approximately at date, an updateNewMessage or updateNewChannelMessage with the from_scheduled flag set, indicating to the sender that the specified message with pending video processing was sent.

- Approximately at date, an updateDeleteScheduledMessages, indicating that the message was flushed from the schedule queue.

- The messages field will contain the scheduled message IDs for the sent messages (initially returned in updateNewScheduledMessage), and sent_messages will contain the real message IDs for the sent messages.

- The scheduled and real message ID for a given message will be at the same vector index, in messages and sent_messages respectively.

### Manipulating the schedule queue

```
updateNewScheduledMessage#39a51dfb message:Message = Update;
updateDeleteScheduledMessages#f2a71983 flags:# peer:Peer messages:Vector<int> sent_messages:flags.0?Vector<int> = Update;

---functions---

messages.getScheduledHistory#f516760b peer:InputPeer hash:long = messages.Messages;
messages.getScheduledMessages#bdbb0464 peer:InputPeer id:Vector<int> = messages.Messages;
messages.sendScheduledMessages#bd38850a peer:InputPeer id:Vector<int> = Updates;
messages.deleteScheduledMessages#59ae2b16 peer:InputPeer id:Vector<int> = Updates;

messages.editMessage#dfd14005 flags:# no_webpage:flags.1?true invert_media:flags.16?true peer:InputPeer id:int message:flags.11?string media:flags.14?InputMedia reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.15?int quick_reply_shortcut_id:flags.17?int = Updates;
```

Clients can manually edit the schedule queue of a certain chat, providing the scheduled message ID obtained from updateNewScheduledMessage.

- messages.getScheduledHistory obtains all messages in the schedule queue for the specified chat

- messages.getScheduledMessages obtains information about specific messages in the schedule queue for the specified chat

- messages.sendScheduledMessages flushes messages from the schedule queue, sending them immediately

- messages.deleteScheduledMessages deletes messages from the schedule queue, without sending them

- messages.editMessage can be used to modify the scheduled date of a specific message in a schedule queue.

Modifying scheduled messages will generate an updateNewScheduledMessage with the same ID, and updated information.
Deleting scheduled messages will generate an updateDeleteScheduledMessages.

