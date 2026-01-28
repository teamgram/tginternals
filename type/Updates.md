# Updates
Object which is perceived by the client without a call on its part when an event occurs.

```
updatesTooLong#e317af7e = Updates;
updateShortMessage#313bc7f8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int user_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShortChatMessage#4d6deea5 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true id:int from_id:long chat_id:long message:string pts:int pts_count:int date:int fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long reply_to:flags.3?MessageReplyHeader entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;
updateShort#78d4dec1 update:Update date:int = Updates;
updatesCombined#725b04c3 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq_start:int seq:int = Updates;
updates#74ae4240 updates:Vector<Update> users:Vector<User> chats:Vector<Chat> date:int seq:int = Updates;
updateShortSentMessage#9015e101 flags:# out:flags.1?true id:int pts:int pts_count:int date:int media:flags.9?MessageMedia entities:flags.7?Vector<MessageEntity> ttl_period:flags.25?int = Updates;

---functions---

contacts.deleteContacts#96a0e00 id:Vector<InputUser> = Updates;
contacts.addContact#e8f463d0 flags:# add_phone_privacy_exception:flags.0?true id:InputUser first_name:string last_name:string phone:string = Updates;
contacts.acceptContact#f831a20f id:InputUser = Updates;
contacts.getLocated#d348bc44 flags:# background:flags.1?true geo_point:InputGeoPoint self_expires:flags.0?int = Updates;
contacts.blockFromReplies#29a8962c flags:# delete_message:flags.0?true delete_history:flags.1?true report_spam:flags.2?true msg_id:int = Updates;

messages.sendMessage#fe05dc9a flags:# no_webpage:flags.1?true silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
messages.sendMedia#ac55d9c1 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
messages.forwardMessages#978928ca flags:# silent:flags.5?true background:flags.6?true with_my_score:flags.8?true drop_author:flags.11?true drop_media_captions:flags.12?true noforwards:flags.14?true allow_paid_floodskip:flags.19?true from_peer:InputPeer id:Vector<int> random_id:Vector<long> to_peer:InputPeer top_msg_id:flags.9?int reply_to:flags.22?InputReplyTo schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut video_timestamp:flags.20?int allow_paid_stars:flags.21?long suggested_post:flags.23?SuggestedPost = Updates;
messages.editChatTitle#73783ffd chat_id:long title:string = Updates;
messages.editChatPhoto#35ddd674 chat_id:long photo:InputChatPhoto = Updates;
messages.deleteChatUser#a2185cab flags:# revoke_history:flags.0?true chat_id:long user_id:InputUser = Updates;
messages.importChatInvite#6c50051c hash:string = Updates;
messages.startBot#e6df7378 bot:InputUser peer:InputPeer random_id:long start_param:string = Updates;
messages.migrateChat#a2875319 chat_id:long = Updates;
messages.sendInlineBotResult#c0cf7646 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true hide_via:flags.11?true peer:InputPeer reply_to:flags.0?InputReplyTo random_id:long query_id:long id:string schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut allow_paid_stars:flags.21?long = Updates;
messages.editMessage#dfd14005 flags:# no_webpage:flags.1?true invert_media:flags.16?true peer:InputPeer id:int message:flags.11?string media:flags.14?InputMedia reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.15?int quick_reply_shortcut_id:flags.17?int = Updates;
messages.getAllDrafts#6a3f8d65 = Updates;
messages.setGameScore#8ef8ecc0 flags:# edit_message:flags.0?true force:flags.1?true peer:InputPeer id:int user_id:InputUser score:int = Updates;
messages.sendScreenshotNotification#a1405817 peer:InputPeer reply_to:InputReplyTo random_id:long = Updates;
messages.sendMultiMedia#1bf89d74 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo multi_media:Vector<InputSingleMedia> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long = Updates;
messages.updatePinnedMessage#d2aaf7ec flags:# silent:flags.0?true unpin:flags.1?true pm_oneside:flags.2?true peer:InputPeer id:int = Updates;
messages.sendVote#10ea6184 peer:InputPeer msg_id:int options:Vector<bytes> = Updates;
messages.getPollResults#73bb643b peer:InputPeer msg_id:int = Updates;
messages.editChatDefaultBannedRights#a5866b41 peer:InputPeer banned_rights:ChatBannedRights = Updates;
messages.sendScheduledMessages#bd38850a peer:InputPeer id:Vector<int> = Updates;
messages.deleteScheduledMessages#59ae2b16 peer:InputPeer id:Vector<int> = Updates;
messages.setHistoryTTL#b80e5fe4 peer:InputPeer period:int = Updates;
messages.setChatTheme#81202c9 peer:InputPeer theme:InputChatTheme = Updates;
messages.hideChatJoinRequest#7fe7e815 flags:# approved:flags.0?true peer:InputPeer user_id:InputUser = Updates;
messages.hideAllChatJoinRequests#e085f4ea flags:# approved:flags.0?true peer:InputPeer link:flags.1?string = Updates;
messages.toggleNoForwards#b11eafa2 peer:InputPeer enabled:Bool = Updates;
messages.sendReaction#d30d78d4 flags:# big:flags.1?true add_to_recent:flags.2?true peer:InputPeer msg_id:int reaction:flags.0?Vector<Reaction> = Updates;
messages.getMessagesReactions#8bba90e6 peer:InputPeer id:Vector<int> = Updates;
messages.setChatAvailableReactions#864b2581 flags:# peer:InputPeer available_reactions:ChatReactions reactions_limit:flags.0?int paid_enabled:flags.1?Bool = Updates;
messages.sendWebViewData#dc0242c8 bot:InputUser random_id:long button_text:string data:string = Updates;
messages.getExtendedMedia#84f80814 peer:InputPeer id:Vector<int> = Updates;
messages.sendBotRequestedPeer#91b2d060 peer:InputPeer msg_id:int button_id:int requested_peers:Vector<InputPeer> = Updates;
messages.setChatWallPaper#8ffacae1 flags:# for_both:flags.3?true revert:flags.4?true peer:InputPeer wallpaper:flags.0?InputWallPaper settings:flags.2?WallPaperSettings id:flags.1?int = Updates;
messages.sendQuickReplyMessages#6c750de1 peer:InputPeer shortcut_id:int id:Vector<int> random_id:Vector<long> = Updates;
messages.deleteQuickReplyMessages#e105e910 shortcut_id:int id:Vector<int> = Updates;
messages.editFactCheck#589ee75 peer:InputPeer msg_id:int text:TextWithEntities = Updates;
messages.deleteFactCheck#d1da940c peer:InputPeer msg_id:int = Updates;
messages.sendPaidReaction#58bbcb50 flags:# peer:InputPeer msg_id:int count:int random_id:long private:flags.0?PaidReactionPrivacy = Updates;
messages.getPaidReactionPrivacy#472455aa = Updates;
messages.toggleTodoCompleted#d3e03124 peer:InputPeer msg_id:int completed:Vector<int> incompleted:Vector<int> = Updates;
messages.appendTodoList#21a61057 peer:InputPeer msg_id:int list:Vector<TodoItem> = Updates;
messages.toggleSuggestedPostApproval#8107455c flags:# reject:flags.1?true peer:InputPeer msg_id:int schedule_date:flags.0?int reject_comment:flags.2?string = Updates;

channels.createChannel#91006707 flags:# broadcast:flags.0?true megagroup:flags.1?true for_import:flags.3?true forum:flags.5?true title:string about:string geo_point:flags.2?InputGeoPoint address:flags.2?string ttl_period:flags.4?int = Updates;
channels.editAdmin#d33c8902 channel:InputChannel user_id:InputUser admin_rights:ChatAdminRights rank:string = Updates;
channels.editTitle#566decd0 channel:InputChannel title:string = Updates;
channels.editPhoto#f12e57c9 channel:InputChannel photo:InputChatPhoto = Updates;
channels.joinChannel#24b524c5 channel:InputChannel = Updates;
channels.leaveChannel#f836aa95 channel:InputChannel = Updates;
channels.deleteChannel#c0111fe3 channel:InputChannel = Updates;
channels.toggleSignatures#418d549c flags:# signatures_enabled:flags.0?true profiles_enabled:flags.1?true channel:InputChannel = Updates;
channels.editBanned#96e6cd81 channel:InputChannel participant:InputPeer banned_rights:ChatBannedRights = Updates;
channels.deleteHistory#9baa9647 flags:# for_everyone:flags.0?true channel:InputChannel max_id:int = Updates;
channels.togglePreHistoryHidden#eabbb94c channel:InputChannel enabled:Bool = Updates;
channels.editCreator#8f38cd1f channel:InputChannel user_id:InputUser password:InputCheckPasswordSRP = Updates;
channels.toggleSlowMode#edd49ef0 channel:InputChannel seconds:int = Updates;
channels.convertToGigagroup#b290c69 channel:InputChannel = Updates;
channels.toggleJoinToSend#e4cb9580 channel:InputChannel enabled:Bool = Updates;
channels.toggleJoinRequest#4c2985b6 channel:InputChannel enabled:Bool = Updates;
channels.toggleForum#3ff75734 channel:InputChannel enabled:Bool tabs:Bool = Updates;
channels.createForumTopic#f40c0224 flags:# channel:InputChannel title:string icon_color:flags.0?int icon_emoji_id:flags.3?long random_id:long send_as:flags.2?InputPeer = Updates;
channels.editForumTopic#f4dfa185 flags:# channel:InputChannel topic_id:int title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = Updates;
channels.updatePinnedForumTopic#6c2d9026 channel:InputChannel topic_id:int pinned:Bool = Updates;
channels.reorderPinnedForumTopics#2950a18f flags:# force:flags.0?true channel:InputChannel order:Vector<int> = Updates;
channels.toggleAntiSpam#68f3e4eb channel:InputChannel enabled:Bool = Updates;
channels.toggleParticipantsHidden#6a6e7854 channel:InputChannel enabled:Bool = Updates;
channels.updateColor#d8aa3671 flags:# for_profile:flags.1?true channel:InputChannel color:flags.2?int background_emoji_id:flags.0?long = Updates;
channels.toggleViewForumAsMessages#9738bb15 channel:InputChannel enabled:Bool = Updates;
channels.updateEmojiStatus#f0d3e6a8 channel:InputChannel emoji_status:EmojiStatus = Updates;
channels.setBoostsToUnblockRestrictions#ad399cee channel:InputChannel boosts:int = Updates;
channels.restrictSponsoredMessages#9ae91519 channel:InputChannel restricted:Bool = Updates;
channels.updatePaidMessagesPrice#4b12327b flags:# broadcast_messages_allowed:flags.0?true channel:InputChannel send_paid_messages_stars:long = Updates;
channels.toggleAutotranslation#167fc0a1 channel:InputChannel enabled:Bool = Updates;

phone.discardCall#b2cbc1c0 flags:# video:flags.0?true peer:InputPhoneCall duration:int reason:PhoneCallDiscardReason connection_id:long = Updates;
phone.setCallRating#59ead627 flags:# user_initiative:flags.0?true peer:InputPhoneCall rating:int comment:string = Updates;
phone.createGroupCall#48cdc6d8 flags:# rtmp_stream:flags.2?true peer:InputPeer random_id:int title:flags.0?string schedule_date:flags.1?int = Updates;
phone.joinGroupCall#8fb53057 flags:# muted:flags.0?true video_stopped:flags.2?true call:InputGroupCall join_as:InputPeer invite_hash:flags.1?string public_key:flags.3?int256 block:flags.3?bytes params:DataJSON = Updates;
phone.leaveGroupCall#500377f9 call:InputGroupCall source:int = Updates;
phone.inviteToGroupCall#7b393160 call:InputGroupCall users:Vector<InputUser> = Updates;
phone.discardGroupCall#7a777135 call:InputGroupCall = Updates;
phone.toggleGroupCallSettings#74bbb43d flags:# reset_invite_hash:flags.1?true call:InputGroupCall join_muted:flags.0?Bool = Updates;
phone.toggleGroupCallRecord#f128c708 flags:# start:flags.0?true video:flags.2?true call:InputGroupCall title:flags.1?string video_portrait:flags.2?Bool = Updates;
phone.editGroupCallParticipant#a5273abf flags:# call:InputGroupCall participant:InputPeer muted:flags.0?Bool volume:flags.1?int raise_hand:flags.2?Bool video_stopped:flags.3?Bool video_paused:flags.4?Bool presentation_paused:flags.5?Bool = Updates;
phone.editGroupCallTitle#1ca6ac0a call:InputGroupCall title:string = Updates;
phone.toggleGroupCallStartSubscription#219c34e6 call:InputGroupCall subscribed:Bool = Updates;
phone.startScheduledGroupCall#5680e342 call:InputGroupCall = Updates;
phone.joinGroupCallPresentation#cbea6bc4 call:InputGroupCall params:DataJSON = Updates;
phone.leaveGroupCallPresentation#1c50d144 call:InputGroupCall = Updates;
phone.createConferenceCall#7d0444bb flags:# muted:flags.0?true video_stopped:flags.2?true join:flags.3?true random_id:int public_key:flags.3?int256 block:flags.3?bytes params:flags.3?DataJSON = Updates;
phone.deleteConferenceCallParticipants#8ca60525 flags:# only_left:flags.0?true kick:flags.1?true call:InputGroupCall ids:Vector<long> block:bytes = Updates;
phone.sendConferenceCallBroadcast#c6701900 call:InputGroupCall block:bytes = Updates;
phone.inviteConferenceCallParticipant#bcf22685 flags:# video:flags.0?true call:InputGroupCall user_id:InputUser = Updates;
phone.declineConferenceCallInvite#3c479971 msg_id:int = Updates;
phone.getGroupCallChainBlocks#ee9f88a6 call:InputGroupCall sub_chain_id:int offset:int limit:int = Updates;

account.getNotifyExceptions#53577479 flags:# compare_sound:flags.1?true compare_stories:flags.2?true peer:flags.0?InputNotifyPeer = Updates;
account.updateConnectedBot#66a08c7e flags:# deleted:flags.1?true rights:flags.0?BusinessBotRights bot:InputUser recipients:InputBusinessBotRecipients = Updates;
account.getBotBusinessConnection#76a86270 connection_id:string = Updates;

folders.editPeerFolders#6847d0ab folder_peers:Vector<InputFolderPeer> = Updates;

payments.assignAppStoreTransaction#80ed747d receipt:bytes purpose:InputStorePaymentPurpose = Updates;
payments.assignPlayMarketTransaction#dffd50d3 receipt:DataJSON purpose:InputStorePaymentPurpose = Updates;
payments.applyGiftCode#f6e26854 slug:string = Updates;
payments.launchPrepaidGiveaway#5ff58f20 peer:InputPeer giveaway_id:long purpose:InputStorePaymentPurpose = Updates;
payments.refundStarsCharge#25ae8f4a user_id:InputUser charge_id:string = Updates;
payments.upgradeStarGift#aed6e4f5 flags:# keep_original_details:flags.0?true stargift:InputSavedStarGift = Updates;
payments.transferStarGift#7f18176a stargift:InputSavedStarGift to_id:InputPeer = Updates;
payments.updateStarGiftPrice#edbe6ccb stargift:InputSavedStarGift resell_amount:StarsAmount = Updates;

chatlists.joinChatlistInvite#a6b1e39a slug:string peers:Vector<InputPeer> = Updates;
chatlists.joinChatlistUpdates#e089f8f5 chatlist:InputChatlist peers:Vector<InputPeer> = Updates;
chatlists.leaveChatlist#74fae13a chatlist:InputChatlist peers:Vector<InputPeer> = Updates;

stories.sendStory#737fc2ec flags:# pinned:flags.2?true noforwards:flags.4?true fwd_modified:flags.7?true peer:InputPeer media:InputMedia media_areas:flags.5?Vector<MediaArea> caption:flags.0?string entities:flags.1?Vector<MessageEntity> privacy_rules:Vector<InputPrivacyRule> random_id:long period:flags.3?int fwd_from_id:flags.6?InputPeer fwd_from_story:flags.6?int albums:flags.8?Vector<int> = Updates;
stories.editStory#b583ba46 flags:# peer:InputPeer id:int media:flags.0?InputMedia media_areas:flags.3?Vector<MediaArea> caption:flags.1?string entities:flags.1?Vector<MessageEntity> privacy_rules:flags.2?Vector<InputPrivacyRule> = Updates;
stories.activateStealthMode#57bbd166 flags:# past:flags.0?true future:flags.1?true = Updates;
stories.sendReaction#7fd736b2 flags:# add_to_recent:flags.0?true peer:InputPeer story_id:int reaction:Reaction = Updates;
stories.getAllReadPeerStories#9b5ae7f9 = Updates;

bots.allowSendMessage#f132e3ef bot:InputUser = Updates;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| updatesTooLong | Too many updates, it is necessary to execute updates.getDifference. |
| updateShortMessage | Info about a message sent to (received from) another user |
| updateShortChatMessage | Shortened constructor containing info on one new incoming text message from a chat |
| updateShort | Shortened constructor containing info on one update not requiring auxiliary data |
| updatesCombined | Constructor for a group of updates. |
| updates | Full constructor of updates |
| updateShortSentMessage | Shortened constructor containing info on one outgoing message to a contact (the destination chat has to be extracted from the method call that returned this object). |


## Methods
| Method | Description |
| ---- | ----------- |
| account.getNotifyExceptions | Returns list of chats with non-default notification settings |
| account.updateConnectedBot | Connect a business bot » to the current account, or to change the current connection settings. |
| account.getBotBusinessConnection | Bots may invoke this method to re-fetch the updateBotBusinessConnect constructor associated with a specific business connection_id, see here » for more info on connected business bots.  This is needed for example for freshly logged in bots that are receiving some updateBotNewBusinessMessage, etc. updates because some users have already connected to the bot before it could login.  In this case, the bot is receiving messages from the business connection, but it hasn't cached the associated updateBotBusinessConnect with info about the connection (can it reply to messages? etc.) yet, and cannot receive the old ones because they were sent when the bot wasn't logged into the session yet.  This method can be used to fetch info about a not-yet-cached business connection, and should not be invoked if the info is already cached or to fetch changes, as eventual changes will automatically be sent as new updateBotBusinessConnect updates to the bot using the usual update delivery methods ». |
| contacts.deleteContacts | Deletes several contacts from the list. |
| contacts.addContact | Add an existing telegram user as contact.Use contacts.importContacts to add contacts by phone number, without knowing their Telegram ID. |
| contacts.acceptContact | If the add contact action bar is active, add that user as contact |
| contacts.getLocated | Get users and geochats near you, see here » for more info. |
| contacts.blockFromReplies | Stop getting notifications about discussion replies of a certain user in @replies |
| messages.sendMessage | Sends a message to a chat |
| messages.sendMedia | Send a media |
| messages.forwardMessages | Forwards messages by their IDs. |
| messages.editChatTitle | Changes chat name and sends a service message on it. |
| messages.editChatPhoto | Changes chat photo and sends a service message on it |
| messages.deleteChatUser | Deletes a user from a chat and sends a service message on it. |
| messages.importChatInvite | Import a chat invite and join a private chat/supergroup/channel |
| messages.startBot | Start a conversation with a bot using a deep linking parameter |
| messages.migrateChat | Turn a basic group into a supergroup |
| messages.sendInlineBotResult | Send a result obtained using messages.getInlineBotResults. |
| messages.editMessage | Edit message |
| messages.getAllDrafts | Return all message drafts.  Returns all the latest updateDraftMessage updates related to all chats with drafts. |
| messages.setGameScore | Use this method to set the score of the specified user in a game sent as a normal message (bots only). |
| messages.sendScreenshotNotification | Notify the other user in a private chat that a screenshot of the chat was taken |
| messages.sendMultiMedia | Send an album or grouped media |
| messages.updatePinnedMessage | Pin a message |
| messages.sendVote | Vote in a pollStarting from layer 159, the vote will be sent from the peer specified using messages.saveDefaultSendAs. |
| messages.getPollResults | Get poll results |
| messages.editChatDefaultBannedRights | Edit the default banned rights of a channel/supergroup/group. |
| messages.sendScheduledMessages | Send scheduled messages right away |
| messages.deleteScheduledMessages | Delete scheduled messages |
| messages.setHistoryTTL | Set maximum Time-To-Live of all messages in the specified chat |
| messages.setChatTheme | Change the chat theme of a certain chat, see here » for more info. |
| messages.hideChatJoinRequest | Dismiss or approve a chat join request related to a specific chat or channel. |
| messages.hideAllChatJoinRequests | Dismiss or approve all join requests related to a specific chat or channel. |
| messages.toggleNoForwards | Enable or disable content protection on a channel or chat |
| messages.sendReaction | React to message.Starting from layer 159, the reaction will be sent from the peer specified using messages.saveDefaultSendAs. |
| messages.getMessagesReactions | Get message reactions » |
| messages.setChatAvailableReactions | Change the set of message reactions » that can be used in a certain group, supergroup or channel |
| messages.sendWebViewData | Used by the user to relay data from an opened reply keyboard bot mini app to the bot that owns it. |
| messages.getExtendedMedia | Fetch updated information about paid media, see here » for the full flow.This method will return an array of updateMessageExtendedMedia updates, only for messages containing already bought paid media.  No information will be returned for messages containing not yet bought paid media. |
| messages.sendBotRequestedPeer | Send one or more chosen peers, as requested by a keyboardButtonRequestPeer button. |
| messages.setChatWallPaper | Set a custom wallpaper » in a specific private chat with another user. |
| messages.sendQuickReplyMessages | Send a quick reply shortcut ». |
| messages.deleteQuickReplyMessages | Delete one or more messages from a quick reply shortcut. This will also emit an updateDeleteQuickReplyMessages update. |
| messages.editFactCheck | Edit/create a fact-check on a message.Can only be used by independent fact-checkers as specified by the appConfig.can_edit_factcheck configuration flag. |
| messages.deleteFactCheck | Delete a fact-check from a message.Can only be used by independent fact-checkers as specified by the appConfig.can_edit_factcheck configuration flag. |
| messages.sendPaidReaction | Sends one or more paid Telegram Star reactions », transferring Telegram Stars » to a channel's balance. |
| messages.getPaidReactionPrivacy | Fetches an updatePaidReactionPrivacy update with the current default paid reaction privacy, see here » for more info. |
| messages.toggleTodoCompleted | Mark one or more items of a todo list » as completed or not completed. |
| messages.appendTodoList | Appends one or more items to a todo list ». |
| messages.toggleSuggestedPostApproval | Approve or reject a suggested post ». |
| channels.createChannel | Create a supergroup/channel. |
| channels.editAdmin | Modify the admin rights of a user in a supergroup/channel. |
| channels.editTitle | Edit the name of a channel/supergroup |
| channels.editPhoto | Change the photo of a channel/supergroup |
| channels.joinChannel | Join a channel/supergroup |
| channels.leaveChannel | Leave a channel/supergroup |
| channels.deleteChannel | Delete a channel/supergroup |
| channels.toggleSignatures | Enable/disable message signatures in channels |
| channels.editBanned | Ban/unban/kick a user in a supergroup/channel. |
| channels.deleteHistory | Delete the history of a supergroup |
| channels.togglePreHistoryHidden | Hide/unhide message history for new channel/supergroup users |
| channels.editCreator | Transfer channel ownership |
| channels.toggleSlowMode | Toggle supergroup slow mode: if enabled, users will only be able to send one message every seconds seconds |
| channels.convertToGigagroup | Convert a supergroup to a gigagroup, when requested by channel suggestions. |
| channels.toggleJoinToSend | Set whether all users should join a discussion group in order to comment on a post » |
| channels.toggleJoinRequest | Set whether all users should request admin approval to join the group ». |
| channels.toggleForum | Enable or disable forum functionality in a supergroup. |
| channels.createForumTopic | Create a forum topic; requires manage_topics rights. |
| channels.editForumTopic | Edit forum topic; requires manage_topics rights. |
| channels.updatePinnedForumTopic | Pin or unpin forum topics |
| channels.reorderPinnedForumTopics | Reorder pinned forum topics |
| channels.toggleAntiSpam | Enable or disable the native antispam system. |
| channels.toggleParticipantsHidden | Hide or display the participants list in a supergroup.The supergroup must have at least hidden_members_group_size_min participants in order to use this method, as specified by the client configuration parameters ». |
| channels.updateColor | Update the accent color and background custom emoji » of a channel. |
| channels.toggleViewForumAsMessages | Users may also choose to display messages from all topics of a forum as if they were sent to a normal group, using a "View as messages" setting in the local client: this setting only affects the current account, and is synced to other logged in sessions using this method.Invoking this method will update the value of the view_forum_as_messages flag of channelFull or dialog and emit an updateChannelViewForumAsMessages. |
| channels.updateEmojiStatus | Set an emoji status for a channel or supergroup. |
| channels.setBoostsToUnblockRestrictions | Admins with ban_users admin rights » may allow users that apply a certain number of booosts » to the group to bypass slow mode » and other » supergroup restrictions, see here » for more info. |
| channels.restrictSponsoredMessages | Disable ads on the specified channel, for all users.Available only after reaching at least the boost level » specified in the channel_restrict_sponsored_level_min » config parameter. |
| channels.updatePaidMessagesPrice | Enable or disable paid messages » in this supergroup or monoforum.Also used to enable or disable monoforums aka direct messages in a channel.Note that passing the ID of the monoforum itself to channel will return a CHANNEL_MONOFORUM_UNSUPPORTED error: pass the ID of the associated channel to edit the settings of the associated monoforum, instead. |
| channels.toggleAutotranslation | Toggle autotranslation in a channel, for all users: see here » for more info. |
| bots.allowSendMessage | Allow the specified bot to send us messages |
| payments.assignAppStoreTransaction | Informs server about a purchase made through the App Store: for official applications only. |
| payments.assignPlayMarketTransaction | Informs server about a purchase made through the Play Store: for official applications only. |
| payments.applyGiftCode | Apply a Telegram Premium giftcode » |
| payments.launchPrepaidGiveaway | Launch a prepaid giveaway ». |
| payments.refundStarsCharge | Refund a Telegram Stars transaction, see here » for more info. |
| payments.upgradeStarGift | Upgrade a gift to a collectible gift: can only be used if the upgrade was already paid by the gift sender; see here » for more info on the full flow (including the different flow to use in case the upgrade was not paid by the gift sender). |
| payments.transferStarGift | Transfer a collectible gift to another user or channel: can only be used if transfer is free (i.e. messageActionStarGiftUnique.transfer_stars is not set); see here » for more info on the full flow (including the different flow to use in case the transfer isn't free). |
| payments.updateStarGiftPrice | A collectible gift we own » can be put up for sale on the gift marketplace » with this method, see here » for more info. |
| phone.discardCall | Refuse or end running call |
| phone.setCallRating | Rate a call, returns info about the rating message sent to the official VoIP bot. |
| phone.createGroupCall | Create a group call or livestream |
| phone.joinGroupCall | Join a group call |
| phone.leaveGroupCall | Leave a group call |
| phone.inviteToGroupCall | Invite a set of users to a group call. |
| phone.discardGroupCall | Terminate a group call |
| phone.toggleGroupCallSettings | Change group call settings |
| phone.toggleGroupCallRecord | Start or stop recording a group call: the recorded audio and video streams will be automatically sent to Saved messages (the chat with ourselves). |
| phone.editGroupCallParticipant | Edit information about a given group call participantNote: flags.N?Bool parameters can have three possible values:- If the TL flag is not set, the previous value will not be changed.- If the TL flag is set and contains a boolTrue, the previous value will be overwritten to true.- If the TL flag is set and contains a boolFalse, the previous value will be overwritten to false. |
| phone.editGroupCallTitle | Edit the title of a group call or livestream |
| phone.toggleGroupCallStartSubscription | Subscribe or unsubscribe to a scheduled group call |
| phone.startScheduledGroupCall | Start a scheduled group call. |
| phone.joinGroupCallPresentation | Start screen sharing in a call |
| phone.leaveGroupCallPresentation | Stop screen sharing in a group call |
| phone.createConferenceCall | Create and optionally join a new conference call. |
| phone.deleteConferenceCallParticipants | Remove participants from a conference call.Exactly one of the only_left and kick flags must be set. |
| phone.sendConferenceCallBroadcast | Broadcast a blockchain block to all members of a conference call, see here » for more info. |
| phone.inviteConferenceCallParticipant | Invite a user to a conference call. |
| phone.declineConferenceCallInvite | Declines a conference call invite. |
| phone.getGroupCallChainBlocks | Fetch the blocks of a conference blockchain ». |
| folders.editPeerFolders | Edit peers in peer folder |
| chatlists.joinChatlistInvite | Import a chat folder deep link », joining some or all the chats in the folder. |
| chatlists.joinChatlistUpdates | Join channels and supergroups recently added to a chat folder deep link ». |
| chatlists.leaveChatlist | Delete a folder imported using a chat folder deep link » |
| stories.sendStory | Uploads a Telegram Story.May also be used in a business connection, not by wrapping the query in invokeWithBusinessConnection », but rather by specifying the ID of a controlled business user in peer. |
| stories.editStory | Edit an uploaded storyMay also be used in a business connection, not by wrapping the query in invokeWithBusinessConnection », but rather by specifying the ID of a controlled business user in peer: in this context, the method can only be used to edit stories posted by the same business bot on behalf of the user with stories.sendStory. |
| stories.activateStealthMode | Activates stories stealth mode, see here » for more info.Will return an updateStoriesStealthMode. |
| stories.sendReaction | React to a story. |
| stories.getAllReadPeerStories | Obtain the latest read story ID for all peers when first logging in, returned as a list of updateReadStories updates, see here » for more info. |


