# Bot API changelog

> The Bot API is an HTTP-based interface created for developers keen on building bots for Telegram.
To learn how to create and set up a bot, please consult our Introduction to Bots »

You will find all changes to our Bot API on this page.

### Recent changes

> Subscribe to @BotNews to be the first to know about the latest updates and join the discussion in @BotTalk

### 2023

#### December 29, 2023

Bot API 7.0

Reactions

- Added the classes ReactionTypeEmoji and ReactionTypeCustomEmoji representing different types of reaction.

- Added updates about a reaction change on a message with non-anonymous reactions, represented by the class MessageReactionUpdated and the field message_reaction in the class Update. The bot must explicitly allow the update to receive it.

- Added updates about reaction changes on a message with anonymous reactions, represented by the class MessageReactionCountUpdated and the field message_reaction_count in the class Update. The bot must explicitly allow the update to receive it.

- Added the method setMessageReaction that allows bots to react to messages.

- Added the field available_reactions to the class Chat.

Replies 2.0

- Added the ability to reply to messages in other chats or forum topics.

- Added the class ExternalReplyInfo and the field external_reply of type ExternalReplyInfo to the class Message, containing information about a message that is replied to by the current message, but can be from another chat or forum topic.

- Added the ability to quote a part of the replied message.

- Added the class TextQuote and the field quote of type TextQuote to the class Message, which contains the part of the replied message text or caption that is quoted in the current message.

- Added the class ReplyParameters and replaced parameters reply_to_message_id and allow_sending_without_reply in the methods copyMessage, sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendSticker, sendVideoNote, sendVoice, sendLocation, sendVenue, sendContact, sendPoll, sendDice, sendInvoice, sendGame, and sendMediaGroup with the field reply_parameters of type ReplyParameters.

Link Preview Customization

- Allowed to explicitly specify the URL that will be used for link preview generation in outgoing text messages.

- Allowed to position link previews above the message text.

- Allowed to choose media size in link previews.

- Added the class LinkPreviewOptions and replaced the parameter disable_web_page_preview with link_preview_options in the methods sendMessage and editMessageText.

- Replaced the field disable_web_page_preview with link_preview_options in the class InputTextMessageContent.

- Added the field link_preview_options to the class Message with information about the link preview options used to send the message.

Block Quotation

- Added support for "blockquote" entities in received messages.

- Added support for "blockquote" entity parsing in "MarkdownV2" and "HTML" parse modes.

- Allowed to explicitly specify "blockquote" entities in formatted texts.

Multiple Message Actions

- Added the method deleteMessages to allow the deletion of multiple messages in a single request.

- Added the method forwardMessages for forwarding of multiple messages in a single request.

- Added the method copyMessages for copying of multiple messages in a single request.

Request for multiple users

- Renamed the class KeyboardButtonRequestUser to KeyboardButtonRequestUsers and added the field max_quantity to it.

- Renamed the field request_user in the class KeyboardButton to request_users. The old name will still work for backward compatibility.

- Added the class UsersShared.

- Replaced the field user_shared in the class Message with the field users_shared.

Chat Boost

- Added updates about chat boost changes, represented by the classes ChatBoostUpdated and ChatBoostRemoved and the fields chat_boost and removed_chat_boost in the class Update. The bot must be an administrator in the chat to receive these updates.

- Added the classes ChatBoostSourcePremium, ChatBoostSourceGiftCode and ChatBoostSourceGiveaway, representing different sources of a chat boost.

- Added the method getUserChatBoosts for obtaining the list of all active boosts a user has contributed to a chat.

Giveaway

- Added the class Giveaway and the field giveaway to the class Message for messages about scheduled giveaways.

- Added the class GiveawayCreated and the field giveaway_created to the class Message for service messages about the creation of a scheduled giveaway.

- Added the class GiveawayWinners and the field giveaway_winners to the class Message for messages about the completion of a giveaway with public winners.

- Added the class GiveawayCompleted and the field giveaway_completed to the class Message for service messages about the completion of a giveaway without public winners.

Web App Changes

- Added the field SettingsButton to the class WebApp.

- Added the fields header_bg_color, accent_text_color, section_bg_color, section_header_text_color, subtitle_text_color, destructive_text_color to the class ThemeParams.

- Web Apps no longer close when the method WebApp.openTelegramLink is called.

Other Changes

- Added support for the fields emoji_status_custom_emoji_id and emoji_status_expiration_date in the class Chat for non-private chats.

- Added the fields accent_color_id, background_custom_emoji_id, profile_accent_color_id, and profile_background_custom_emoji_id to the class Chat.

- Added the field has_visible_history to the class Chat.

- Added the class MessageOrigin and replaced the fields forward_from, forward_from_chat, forward_from_message_id, forward_signature, forward_sender_name, and forward_date with the field forward_origin of type MessageOrigin in the class Message.

- Improved documentation for the field message of the class callbackQuery and the field pinned_message of the class Message by adding the classes MaybeInaccessibleMessage and InaccessibleMessage.

#### September 22, 2023

Bot API 6.9

- Added the new administrator privileges can_post_stories, can_edit_stories and can_delete_stories to the classes ChatMemberAdministrator and ChatAdministratorRights.

- Added the parameters can_post_stories, can_edit_stories and can_delete_stories to the method promoteChatMember. Currently, bots have no use for these privileges besides assigning them to other administrators.

- Added the ability to set any header color for Web App using the method setHeaderColor.

- Added the field CloudStorage to the class WebApp.

- Added the methods requestWriteAccess and requestContact to the class WebApp.

- Added Web App events writeAccessRequested and contactRequested.

- Added the fields from_request and from_attachment_menu to the class WriteAccessAllowed.

- Added the fields added_to_attachment_menu and allows_write_to_pm to the class WebAppUser.

#### August 18, 2023

Bot API 6.8

- Added the field story to the class Message for messages with forwarded stories. Currently, it holds no information.

- Added the field voter_chat to the class PollAnswer, to contain channel chat voters in Polls. For backward compatibility, the field user in such objects will contain the user 136817688 (@Channel_Bot).

- Added the field emoji_status_expiration_date to the class Chat.

- Added the method unpinAllGeneralForumTopicMessages.

- Increased to 512 characters the maximum length of the startapp parameter in direct Web App links.

#### April 21, 2023

Bot API 6.7

- Added support for launching Web Apps from inline query results by replacing the parameters switch_pm_text and switch_pm_parameter of the method answerInlineQuery with the parameter button of type InlineQueryResultsButton.

- Added the field web_app_name to the class WriteAccessAllowed.

- Added the field switch_inline_query_chosen_chat of the type SwitchInlineQueryChosenChat to the class InlineKeyboardButton, which allows bots to switch to inline mode in a chosen chat of the given type.

- Added the field via_chat_folder_invite_link to the class ChatMemberUpdated.

- Added the ability to set different bot names for different user languages using the method setMyName.

- Added the ability to get the current bot name in the given language as the class BotName using the method getMyName.

- Added the ability to change bot settings from the bot's profile in official Telegram apps, including the ability to set animated profile photos.

- Added the ability to specify custom emoji entities using HTML and MarkdownV2 formatting options for bots that purchased additional usernames on Fragment.

#### March 9, 2023

Bot API 6.6

- Added the ability to set different bot descriptions for different user languages using the method setMyDescription.

- Added the ability to get the current bot description in the given language as the class BotDescription using the method getMyDescription.

- Added the ability to set different bot short descriptions for different user languages using the method setMyShortDescription.

- Added the ability to get the current bot short description in the given language as the class BotShortDescription using the method getMyShortDescription.

- Added the parameter emoji to the method sendSticker to specify an emoji for just uploaded stickers.

- Added support for the creation of custom emoji sticker sets in createNewStickerSet.

- Added the parameter needs_repainting to the method createNewStickerSet to automatically change the color of emoji based on context (e.g., use text color in messages, accent color in statuses, etc.).

- Added the field needs_repainting to the class Sticker.

- Replaced the parameters png_sticker, tgs_sticker, webm_sticker, emojis and mask_position in the method addStickerToSet with the parameter sticker of the type InputSticker.

- Added support for the creation of sticker sets with multiple initial stickers in createNewStickerSet by replacing the parameters png_sticker, tgs_sticker, webm_sticker, emojis and mask_position with the parameters stickers and sticker_format.

- Added support for .WEBP files in createNewStickerSet and addStickerToSet.

- Added support for .WEBP, .TGS, and .WEBM files in uploadStickerFile by replacing the parameter png_sticker in the method uploadStickerFile with the parameters sticker and sticker_format.

- Added the ability to specify search keywords for stickers added to sticker sets.

- Added the method setCustomEmojiStickerSetThumbnail for editing the thumbnail of custom emoji sticker sets created by the bot.

- Added the method setStickerSetTitle for editing the title of sticker sets created by the bot.

- Added the method deleteStickerSet for complete deletion of a given sticker set that was created by the bot.

- Added the method setStickerEmojiList for changing the list of emoji associated with a sticker.

- Added the method setStickerKeywords for changing the search keywords assigned to a sticker.

- Added the method setStickerMaskPosition for changing the mask position of a mask sticker.

- Renamed the field thumb in the classes Animation, Audio, Document, Sticker, Video, VideoNote, InputMediaAnimation, InputMediaAudio, InputMediaDocument, InputMediaVideo, StickerSet to thumbnail.

- Renamed the parameter thumb in the methods sendAnimation, sendAudio, sendDocument, sendVideo, sendVideoNote to thumbnail.

- Renamed the method setStickerSetThumb to setStickerSetThumbnail and its parameter thumb to thumbnail.

- Renamed the fields thumb_url, thumb_width, and thumb_height in the classes InlineQueryResultArticle, InlineQueryResultContact, InlineQueryResultDocument, InlineQueryResultLocation, and InlineQueryResultVenue to thumbnail_url, thumbnail_width, and thumbnail_height respectively.

- Renamed the field thumb_url in the classes InlineQueryResultPhoto and InlineQueryResultVideo to thumbnail_url.

- Renamed the fields thumb_url and thumb_mime_type in the classes InlineQueryResultGif, and InlineQueryResultMpeg4Gif to thumbnail_url and thumbnail_mime_type respectively.

#### February 3, 2023

Bot API 6.5

- Added requests for users and chats and support for granular media permissions.

- Added the class KeyboardButtonRequestUser and the field request_user to the class KeyboardButton.

- Added the class KeyboardButtonRequestChat and the field request_chat to the class KeyboardButton.

- Added the classes UserShared, ChatShared and the fields user_shared, and chat_shared to the class Message.

- Replaced the fields can_send_media_messages in the classes ChatMemberRestricted and ChatPermissions with separate fields can_send_audios, can_send_documents, can_send_photos, can_send_videos, can_send_video_notes, and can_send_voice_notes for different media types.

- Added the parameter use_independent_chat_permissions to the methods restrictChatMember and setChatPermissions.

- Added the field user_chat_id to the class ChatJoinRequest.

### 2022

#### December 30, 2022

Bot API 6.4

- Added the field is_persistent to the class ReplyKeyboardMarkup, allowing to control when the keyboard is shown.

- Added the parameter has_spoiler to the methods sendPhoto, sendVideo, and sendAnimation.

- Added the field has_spoiler to the classes InputMediaPhoto, InputMediaVideo, and InputMediaAnimation.

- Added the field has_media_spoiler to the class Message.

- The parameters name and icon_custom_emoji_id of the method editForumTopic are now optional. If they are omitted, the existing values are kept.

- Added the classes ForumTopicEdited, GeneralForumTopicHidden, GeneralForumTopicUnhidden, and WriteAccessAllowed and the fields forum_topic_edited, general_forum_topic_hidden, general_forum_topic_unhidden, and write_access_allowed to the class Message.

- Added the methods editGeneralForumTopic, closeGeneralForumTopic, reopenGeneralForumTopic, hideGeneralForumTopic, unhideGeneralForumTopic for managing the General topic in forums.

- Added the parameter message_thread_id to the method sendChatAction for sending chat actions to a specific message thread or a forum topic.

- Added the field has_hidden_members to the class Chat. Note that the method getChatMember is only guaranteed to work if the bot is an administrator in the chat.

- Added the field has_aggressive_anti_spam_enabled to the class Chat.

- Added Web App events qrTextReceived and clipboardTextReceived.

- Added the field platform to the class WebApp.

- Added the methods showScanQrPopup, closeScanQrPopup, and readTextFromClipboard to the class WebApp.

- Added the parameter options to the method openLink of the class WebApp.

#### November 5, 2022

Bot API 6.3

- Added support for Topics in Groups.

- Added the field is_forum to the class Chat.

- Added the fields is_topic_message and message_thread_id to the class Message to allow detection of messages belonging to a forum topic and their message thread identifier.

- Added the classes ForumTopicCreated, ForumTopicClosed, and ForumTopicReopened and the fields forum_topic_created, forum_topic_closed, and forum_topic_reopened to the class Message. Note that service messages about forum topic creation can't be deleted with the deleteMessage method.

- Added the field can_manage_topics to the classes ChatAdministratorRights, ChatPermissions, ChatMemberAdministrator, and ChatMemberRestricted.

- Added the parameter can_manage_topics to the method promoteChatMember.

- Added the methods createForumTopic, editForumTopic, closeForumTopic, reopenForumTopic, deleteForumTopic, unpinAllForumTopicMessages, and getForumTopicIconStickers for forum topic management.

- Added the parameter message_thread_id to the methods sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendSticker, sendVideoNote, sendVoice, sendLocation, sendVenue, sendContact, sendPoll, sendDice, sendInvoice, sendGame, sendMediaGroup, copyMessage, forwardMessage to support sending of messages to a forum topic.

- Added support for Multiple Usernames via the field active_usernames in the class Chat.

- Added the field emoji_status_custom_emoji_id to the class Chat.

#### August 12, 2022

Bot API 6.2

Custom Emoji Support

- Added the MessageEntity type "custom_emoji".

- Added the field custom_emoji_id to the class MessageEntity for "custom_emoji" entities.

- Added the method getCustomEmojiStickers.

- Added the fields type and custom_emoji_id to the class Sticker.

- Added the field sticker_type to the class StickerSet, describing the type of stickers in the set.

- The field contains_masks has been removed from the documentation of the class StickerSet. The field is still returned in the object for backward compatibility, but new bots should use the field sticker_type instead.

- Added the parameter sticker_type to the method createNewStickerSet.

- The parameter contains_masks has been removed from the documentation of the method createNewStickerSet. The parameter will still work for backward compatibility, but new bots should use the parameter sticker_type instead.

Web App Improvements

- Added the field isClosingConfirmationEnabled and the methods enableClosingConfirmation, disableClosingConfirmation, showPopup, showAlert, showConfirm to the class WebApp.

- Added the field is_premium to the class WebAppUser.

- Added the event popupClosed.

Other Changes

- Added the field has_restricted_voice_and_video_messages to the class Chat to support the new setting.

#### June 20, 2022

Bot API 6.1

Media in Descriptions

- Added support for photos and videos in the 'What can this bot do?' section (shown on the bot's start screen). Use BotFather to set up media.

Web App Improvements

- Added the fields version, headerColor, backgroundColor, BackButton, HapticFeedback and the methods isVersionAtLeast, setHeaderColor, setBackgroundColor, openLink, openTelegramLink, openInvoice to the class WebApp.

- Added the field secondary_bg_color to the class ThemeParams.

- Added the method offClick to the class MainButton.

- Added the fields chat, can_send_after to the class WebAppInitData.

- Added the events backButtonClicked, settingsButtonClicked, invoiceClosed.

Join Requests & Payments

- Added the fields join_to_send_messages and join_by_request to the class Chat.

- Added the ability to process join requests which were created without an invite link. Bots will receive a "chat_join_request" update as usual.

- Added the method createInvoiceLink to generate an HTTP link for an invoice.

Telegram Premium Support (more info)

- The maximum value of the field file_size in the classes Animation, Audio, Document, Video, Voice, and File can no longer be stored in a signed 32-bit integer type. This change is necessary to support 4GB files uploaded by premium accounts.

- Added the field is_premium to the class User.

- Added the field premium_animation to the class Sticker.

Attachment Menu Integration

- Added the field added_to_attachment_menu to the class User.

- Bots integrated in the attachment menu can now be used in groups, supergroups and channels.

- Added support for t.me links that can be used to select the chat in which the attachment menu with the bot will be opened.

Other Changes

- Added the parameter secret_token to the method setWebhook.

- As previously announced, only HTTPS links are now allowed in login_url inline keyboard buttons.

#### April 16, 2022

Bot API 6.0

- Added support for Web Apps, see the detailed manual here. (blog announcement)

- Added the class WebAppInfo and the fields web_app to the classes KeyboardButton and InlineKeyboardButton.

- Added the class SentWebAppMessage and the method answerWebAppQuery for sending an answer to a Web App query, which originated from an inline button of the 'web_app' type.

- Added the class WebAppData and the field web_app_data to the class Message.

- Added the class MenuButton and the methods setChatMenuButton and getChatMenuButton for managing the behavior of the bot's menu button in private chats.

- Added the class ChatAdministratorRights and the methods setMyDefaultAdministratorRights and getMyDefaultAdministratorRights for managing the bot's default administrator rights.

- Added support for t.me links that can be used to add the bot to groups and channels as an administrator.

- Added the field last_synchronization_error_date to the class WebhookInfo.

- Renamed the field can_manage_voice_chats to can_manage_video_chats in the class ChatMemberAdministrator. The old field will remain temporarily available.

- Renamed the parameter can_manage_voice_chats to can_manage_video_chats in the method promoteChatMember. The old parameter will remain temporarily available.

- Renamed the fields voice_chat_scheduled, voice_chat_started, voice_chat_ended, and voice_chat_participants_invited to video_chat_scheduled, video_chat_started, video_chat_ended, and video_chat_participants_invited in the class Message. The old fields will remain temporarily available.

---

> WARNING! 
After the next update, only HTTPS links will be allowed in login_url inline keyboard buttons.

---

#### January 31, 2022

Bot API 5.7

- Added support for Video Stickers.

- Added the field is_video to the classes Sticker and StickerSet.

- Added the parameter webm_sticker to the methods createNewStickerSet and addStickerToSet.

### 2021

#### December 30, 2021

Bot API 5.6

- Improved support for Protected Content.

- Added the parameter protect_content to the methods sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendSticker, sendVideoNote, sendVoice, sendLocation, sendVenue, sendContact, sendPoll, sendDice, sendInvoice, sendGame, sendMediaGroup, copyMessage, forwardMessage to allow sending messages with protected content to any chat.

- Added support for spoiler entities, which will work in Telegram versions released after December 30, 2021. Older clients will display unsupported message.

- Added new MessageEntity type "spoiler".

- Added the ability to specify spoiler entities using HTML and MarkdownV2 formatting options.

#### December 7, 2021

Bot API 5.5

- Bots are now allowed to contact users who sent a join request to a chat where the bot is an administrator with the can_invite_users administrator right – even if the user never interacted with the bot before.

- Added support for mentioning users by their ID in inline keyboards. This will only work in Telegram versions released after December 7, 2021. Older clients will display unsupported message.

- Added the methods banChatSenderChat and unbanChatSenderChat for banning and unbanning channel chats in supergroups and channels.

- Added the field has_private_forwards to the class Chat for private chats, which can be used to check the possibility of mentioning the user by their ID.

- Added the field has_protected_content to the classes Chat and Message.

- Added the field is_automatic_forward to the class Message.

Note: After this update it will become impossible to forward messages from some chats. Use the fields has_protected_content in the classes Message and Chat to check this.

Note: After this update users are able to send messages on behalf of channels they own. Bots are expected to use the field sender_chat in the class Message to correctly support such messages.

Note: As previously announced, user identifiers can now have up to 52 significant bits and require a 64-bit integer or double-precision float type to be stored safely.

#### November 5, 2021

Bot API 5.4

- Added the the parameter creates_join_request to the methods createChatInviteLink and editChatInviteLink for managing chat invite links that create join requests (read more about this on our blog).

- Added the fields creates_join_request and pending_join_request_count to the class ChatInviteLink.

- Added the field name to the class ChatInviteLink and the parameters name to the methods createChatInviteLink and editChatInviteLink for managing invite link names.

- Added updates about new requests to join the chat, represented by the class ChatJoinRequest and the field chat_join_request in the Update class. The bot must be an administrator in the chat with the can_invite_users administrator right to receive these updates.

- Added the methods approveChatJoinRequest and declineChatJoinRequest for managing requests to join the chat.

- Added support for the choose_sticker action in the method sendChatAction.

---

> WARNING! 
User identifiers will become bigger than 2^31 - 1 before the end of this year and it will be no longer possible to store them in a signed 32-bit integer type. User identifiers will have up to 52 significant bits, so a 64-bit integer or double-precision float type would still be safe for storing them. Please make sure that your code can correctly handle such user identifiers.

---

#### June 25, 2021

Bot API 5.3

Personalized Commands

- Bots can now show lists of commands tailored to specific situations - including localized commands for users with different languages, as well as different commands based on chat type or for specific chats, and special lists of commands for chat admins.

- Added the class BotCommandScope, describing the scope to which bot commands apply.

- Added the parameters scope and language_code to the method setMyCommands to allow bots specify different commands for different chats and users.

- Added the parameters scope and language_code to the method getMyCommands.

- Added the method deleteMyCommands to allow deletion of the bot's commands for the given scope and user language.

- Improved visibility of bot commands in Telegram apps with the new 'Menu' button in chats with bots, read more on the blog.

Custom Placeholders

- Added the ability to specify a custom input field placeholder in the classes ReplyKeyboardMarkup and ForceReply.

And More

- Improved documentation of the class ChatMember by splitting it into 6 subclasses.

- Renamed the method kickChatMember to banChatMember. The old method name can still be used.

- Renamed the method getChatMembersCount to getChatMemberCount. The old method name can still be used.

- Values of the field file_unique_id in objects of the type PhotoSize and of the fields small_file_unique_id and big_file_unique_id in objects of the type ChatPhoto were changed.

---

> WARNING! 
After one of the upcoming Bot API updates, user identifiers will become bigger than 2^31 - 1 and it will be no longer possible to store them in a signed 32-bit integer type. User identifiers will have up to 52 significant bits, so a 64-bit integer or double-precision float type would still be safe for storing them. Please make sure that your code can correctly handle such user identifiers.

---

#### April 26, 2021

Bot API 5.2

- Support for Payments 2.0, see this manual for more details about the Bot Payments API.

- Added the type InputInvoiceMessageContent to support sending invoices as inline query results.

- Allowed sending invoices to group, supergroup and channel chats.

- Added the fields max_tip_amount and suggested_tip_amounts to the method sendInvoice to allow adding optional tips to the payment.

- The parameter start_parameter of the method sendInvoice became optional. If the parameter isn't specified, the invoice can be paid directly from forwarded messages.

- Added the field chat_type to the class InlineQuery, containing the type of the chat, from which the inline request was sent.

- Added the type VoiceChatScheduled and the field voice_chat_scheduled to the class Message.

- Fixed an error in sendChatAction documentation to correctly mention "record_voice" and "upload_voice" instead of "record_audio" and "upload_audio" for related to voice note actions. Old action names will still work for backward compatibility.

---

> WARNING! 
After the next Bot API update (Bot API 5.3) there will be a one-time change of the value of the field file_unique_id in objects of the type PhotoSize and of the fields small_file_unique_id and big_file_unique_id in objects of the type ChatPhoto.

---

> WARNING! 
Service messages about non-bot users joining the chat will be soon removed from large groups. We recommend using the "chat_member" update as a replacement.

---

> WARNING! 
After one of the upcoming Bot API updates, user identifiers will become bigger than 2^31 - 1 and it will be no longer possible to store them in a signed 32-bit integer type. User identifiers will have up to 52 significant bits, so a 64-bit integer or double-precision float type would still be safe for storing them. Please make sure that your code can correctly handle such user identifiers.

---

#### March 9, 2021

Bot API 5.1

Added two new update types

- Added updates about member status changes in chats, represented by the class ChatMemberUpdated and the fields my_chat_member and chat_member in the Update class. The bot must be an administrator in the chat to receive chat_member updates about other chat members. By default, only my_chat_member updates about the bot itself are received.

Improved Invite Links

- Added the class ChatInviteLink, representing an invite link to a chat.

- Added the method createChatInviteLink, which can be used to create new invite links in addition to the primary invite link.

- Added the method editChatInviteLink, which can be used to edit non-primary invite links created by the bot.

- Added the method revokeChatInviteLink, which can be used to revoke invite links created by the bot.

Voice Chat Info

- Added the type VoiceChatStarted and the field voice_chat_started to the class Message.

- Added the type VoiceChatEnded and the field voice_chat_ended to the class Message.

- Added the type VoiceChatParticipantsInvited and the field voice_chat_participants_invited to the class Message.

- Added the new administrator privilege can_manage_voice_chats to the class ChatMember and parameter can_manage_voice_chats to the method promoteChatMember. For now, bots can use this privilege only for passing to other administrators.

And More

- Added the type MessageAutoDeleteTimerChanged and the field message_auto_delete_timer_changed to the class Message.

- Added the parameter revoke_messages to the method kickChatMember, allowing to delete all messages from a group for the user who is being removed.

- Added the new administrator privilege can_manage_chat to the class ChatMember and parameter can_manage_chat to the method promoteChatMember. This administrator right is implied by any other administrator privilege.

- Supported the new bowling animation for the random dice. Choose between different animations (dice, darts, basketball, football, bowling, slot machine) by specifying the emoji parameter in the method sendDice.

---

> WARNING! 
After one of the upcoming Bot API updates, some user identifiers will become bigger than 2^31 - 1 and it will be no longer possible to store them in a signed 32-bit integer type. User identifiers will have up to 52 significant bits, so a 64-bit integer or double-precision float type would still be safe for storing them. Please make sure that your code can correctly handle such user identifiers.

---

### 2020

#### November 4, 2020

Introducing Bot API 5.0

Run Your Own Bot API Server

- Bot API source code is now available at telegram-bot-api. You can now run your own Bot API server locally, boosting your bots' performance.

- Added the method logOut, which can be used to log out from the cloud Bot API server before launching your bot locally. You must log out the bot before running it locally, otherwise there is no guarantee that the bot will receive all updates.

- Added the method close, which can be used to close the bot instance before moving it from one local server to another.

Transfer Bot Ownership

- You can now use @BotFather to transfer your existing bots to another Telegram account.

Webhooks

- Added the parameter ip_address to the method setWebhook, allowing to bypass DNS resolving and use the specified fixed IP address to send webhook requests.

- Added the field ip_address to the class WebhookInfo, containing the current IP address used for webhook connections creation.

- Added the ability to drop all pending updates when changing webhook URL using the parameter drop_pending_updates in the methods setWebhook and deleteWebhook.

Working with Groups

- The getChat request now returns the user's bio for private chats if available.

- The getChat request now returns the identifier of the linked chat for supergroups and channels, i.e. the discussion group identifier for a channel and vice versa.

- The getChat request now returns the location to which the supergroup is connected (see Local Groups). Added the class ChatLocation to represent the location.

- Added the parameter only_if_banned to the method unbanChatMember to allow safe unban.

Working with Files

- Added the field file_name to the classes Audio and Video, containing the name of the original file.

- Added the ability to disable server-side file content type detection using the parameter disable_content_type_detection in the method sendDocument and the class inputMediaDocument.

Multiple Pinned Messages

- Added the ability to pin messages in private chats.

- Added the parameter message_id to the method unpinChatMessage to allow unpinning of the specific pinned message.

- Added the method unpinAllChatMessages, which can be used to unpin all pinned messages in a chat.

File Albums

- Added support for sending and receiving audio and document albums in the method sendMediaGroup.

Live Locations

- Added the field live_period to the class Location, representing a maximum period for which the live location can be updated.

- Added support for live location [heading](https://en.wikipedia.org/wiki/Heading_(navigation&#41;): added the field heading to the classes Location, InlineQueryResultLocation, InputLocationMessageContent and the parameter heading to the methods sendLocation and editMessageLiveLocation.

- Added support for proximity alerts in live locations: added the field proximity_alert_radius to the classes Location, InlineQueryResultLocation, InputLocationMessageContent and the parameter proximity_alert_radius to the methods sendLocation and editMessageLiveLocation.

- Added the type ProximityAlertTriggered and the field proximity_alert_triggered to the class Message.

- Added possibility to specify the horizontal accuracy of a location. Added the field horizontal_accuracy to the classes Location, InlineQueryResultLocation, InputLocationMessageContent and the parameter horizontal_accuracy to the methods sendLocation and editMessageLiveLocation.

Anonymous Admins

- Added the field sender_chat to the class Message, containing the sender of a message which is a chat (group or channel). For backward compatibility in non-channel chats, the field from in such messages will contain the user 777000 for messages automatically forwarded to the discussion group and the user 1087968824 (@GroupAnonymousBot) for messages from anonymous group administrators.

- Added the field is_anonymous to the class chatMember, which can be used to distinguish anonymous chat administrators.

- Added the parameter is_anonymous to the method promoteChatMember, which allows to promote anonymous chat administrators. The bot itself should have the is_anonymous right to do this. Despite the fact that bots can have the is_anonymous right, they will never appear as anonymous in the chat. Bots can use the right only for passing to other administrators.

- Added the custom title of an anonymous message sender to the class Message as author_signature.

And More

- Added the method copyMessage, which sends a copy of any message.

- Maximum poll question length increased to 300.

- Added the ability to manually specify text entities instead of specifying the parse_mode in the classes InputMediaPhoto, InputMediaVideo, InputMediaAnimation, InputMediaAudio, InputMediaDocument, InlineQueryResultPhoto, InlineQueryResultGif, InlineQueryResultMpeg4Gif, InlineQueryResultVideo, InlineQueryResultAudio, InlineQueryResultVoice, InlineQueryResultDocument, InlineQueryResultCachedPhoto, InlineQueryResultCachedGif, InlineQueryResultCachedMpeg4Gif, InlineQueryResultCachedVideo, InlineQueryResultCachedAudio, InlineQueryResultCachedVoice, InlineQueryResultCachedDocument, InputTextMessageContent and the methods sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendVoice, sendPoll, editMessageText, editMessageCaption.

- Added the fields google_place_id and google_place_type to the classes Venue, InlineQueryResultVenue, InputVenueMessageContent and the optional parameters google_place_id and google_place_type to the method sendVenue to support Google Places as a venue API provider.

- Added the field allow_sending_without_reply to the methods sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendSticker, sendVideoNote, sendVoice, sendLocation, sendVenue, sendContact, sendPoll, sendDice, sendInvoice, sendGame, sendMediaGroup to allow sending messages not a as reply if the replied-to message has already been deleted.

And Last but not Least

- Supported the new football and slot machine animations for the random dice. Choose between different animations (dice, darts, basketball, football, slot machine) by specifying the emoji parameter in the method sendDice.

#### June 4, 2020

Bot API 4.9

- Added the new field via_bot to the Message object. You can now know which bot was used to send a message.

- Supported video thumbnails for inline GIF and MPEG4 animations.

- Supported the new basketball animation for the random dice. Choose between different animations (dice, darts, basketball) by specifying the emoji parameter in the method sendDice.

#### April 24, 2020

Bot API 4.8

- Supported explanations for Quizzes 2.0. Add explanations by specifying the parameters explanation and explanation_parse_mode in the method sendPoll.

- Added the fields explanation and explanation_entities to the Poll object.

- Supported timed polls that automatically close at a certain date and time. Set up by specifying the parameter open_period or close_date in the method sendPoll.

- Added the fields open_period and close_date to the Poll object.

- Supported the new darts animation for the dice mini-game. Choose between the default dice animation and darts animation by specifying the parameter emoji in the method sendDice.

- Added the field emoji to the Dice object.

#### March 30, 2020

Bot API 4.7

- Added the method sendDice for sending a dice message, which will have a random value from 1 to 6. (Yes, we're aware of the "proper" singular of die. But it's awkward, and we decided to help it change. One dice at a time!)

- Added the field dice to the Message object.

- Added the method getMyCommands for getting the current list of the bot's commands.

- Added the method setMyCommands for changing the list of the bot's commands through the Bot API instead of @BotFather.

- Added the ability to create animated sticker sets by specifying the parameter tgs_sticker instead of png_sticker in the method createNewStickerSet.

- Added the ability to add animated stickers to sets created by the bot by specifying the parameter tgs_sticker instead of png_sticker in the method addStickerToSet.

- Added the field thumb to the StickerSet object.

- Added the ability to change thumbnails of sticker sets created by the bot using the method setStickerSetThumb.

#### January 23, 2020

Bot API 4.6

- Supported Polls 2.0.

- Added the ability to send non-anonymous, multiple answer, and quiz-style polls: added the parameters is_anonymous, type, allows_multiple_answers, correct_option_id, is_closed options to the method sendPoll.

- Added the object KeyboardButtonPollType and the field request_poll to the object KeyboardButton.

- Added updates about changes of user answers in non-anonymous polls, represented by the object PollAnswer and the field poll_answer in the Update object.

- Added the fields total_voter_count, is_anonymous, type, allows_multiple_answers, correct_option_id to the Poll object.

- Bots can now send polls to private chats.

- Added more information about the bot in response to the getMe request: added the fields can_join_groups, can_read_all_group_messages and supports_inline_queries to the User object.

- Added the optional field language to the MessageEntity object.

### 2019

#### December 31, 2019

Bot API 4.5

- Added support for two new MessageEntity types, underline and strikethrough.

- Added support for nested MessageEntity objects. Entities can now contain other entities. If two entities have common characters then one of them is fully contained inside the other.

- Added support for nested entities and the new tags <u>/<ins> (for underlined text) and <s>/<strike>/<del> (for strikethrough text) in parse mode HTML.

- Added a new parse mode, MarkdownV2, which supports nested entities and two new entities __ (for underlined text) and ~ (for strikethrough text). Parse mode Markdown remains unchanged for backward compatibility.

- Added the field file_unique_id to the objects Animation, Audio, Document, PassportFile, PhotoSize, Sticker, Video, VideoNote, Voice, File and the fields small_file_unique_id and big_file_unique_id to the object ChatPhoto. The new fields contain a unique file identifier, which is supposed to be the same over time and for different bots, but can't be used to download or reuse the file.

- Added the field custom_title to the ChatMember object.

- Added the new method setChatAdministratorCustomTitle to manage the custom titles of administrators promoted by the bot.

- Added the field slow_mode_delay to the Chat object.

#### July 29, 2019

Bot API 4.4

- Added support for animated stickers. New field is_animated in Sticker and StickerSet objects, animated stickers can now be used in sendSticker and InlineQueryResultCachedSticker.

- Added support for default permissions in groups. New object ChatPermissions, containing actions which a member can take in a chat. New field permissions in the Chat object; new method setChatPermissions.

- The field all_members_are_administrators has been removed from the documentation for the Chat object. The field is still returned in the object for backward compatibility, but new bots should use the permissions field instead.

- Added support for more permissions for group and supergroup members: added the new field can_send_polls to ChatMember object, added can_change_info, can_invite_users, can_pin_messages in ChatMember object for restricted users (previously available only for administrators).

- The method restrictChatMember now takes the new user permissions in a single argument of the type ChatPermissions. The old way of passing parameters will keep working for a while for backward compatibility.

- Added description support for basic groups (previously available in supergroups and channel chats). You can pass a group's chat_id to setChatDescription and receive the group's description in the Chat object in the response to getChat method.

- Added invite_link support for basic groups (previously available in supergroups and channel chats). You can pass a group's chat_id to exportChatInviteLink and receive the group's invite link in the Chat object in the response to getChat method.

- File identifiers from the ChatPhoto object are now invalidated and can no longer be used whenever the photo is changed.

- All webhook requests from the Bot API are now coming from the subnets 149.154.160.0/20 and 91.108.4.0/22. Most users won't need to do anything to continue receiving webhooks. If you control inbound access with a firewall, you may need to update your configuration. You can always find the list of actual IP addresses of servers used to send webhooks there: https://core.telegram.org/bots/webhooks.

- As of the next Bot API update (version 4.5), nested MessageEntity objects will be allowed in message texts and captions. Please make sure that your code can correctly handle such entities.

#### May 31, 2019

Bot API 4.3

- Added support for Seamless Telegram Login on external websites.

- Added the new object LoginUrl and the new field login_url to the InlineKeyboardButton object which allows to automatically authorize users before they go to a URL specified by the bot. Users will be asked to confirm authorization in their Telegram app (needs version 5.7 or higher) when they press the button:

Also in this update:

- Added the field reply_markup to the Message object, containing the inline keyboard attached to the message.

- If a message with an inline keyboard is forwarded, the forwarded message will now have an inline keyboard if the keyboard contained only url and login_url buttons or if the message was sent via a bot and the keyboard contained only url, login_url, switch_inline_query or switch_inline_query_current_chat buttons. In the latter case, switch_inline_query_current_chat buttons are replaced with switch_inline_query buttons.

- Bots now receive the edited_message Update even if only Message.reply_markup has changed.

- Bots that have the can_edit_messages right in a channel can now use the method editMessageReplyMarkup for messages written by other administrators forever without the 48 hours limit.

- Don't forget that starting in July 2019, webhook requests from Bot API will be coming from the subnets 149.154.160.0/20 and 91.108.4.0/22. Most users won't need to do anything to continue receiving webhooks. If you control inbound access with a firewall, you may need to update your configuration. You can always find the list of actual IP addresses of servers used to send webhooks there: https://core.telegram.org/bots/webhooks.

#### April 14, 2019

Bot API 4.2

- Added support for native polls: added the object Poll, the methods sendPoll and stopPoll and the field poll in the Message and Update objects.

- The method deleteMessage can now be used to delete messages sent by a user to the bot in private chats within 48 hours.

- Added support for pinned messages in basic groups in addition to supergroups and channel chats: you can pass group's chat_id to pinChatMessage and unpinChatMessage, and receive the pinned group message in Chat object.

- Added the field is_member to the ChatMember object, which can be used to find whether a restricted user is a member of the chat.

- Added the field forward_sender_name to the Message object, containing name of the sender who has opted to hide their account.

- Starting in July 2019, webhook requests from Bot API will be coming from the subnets 149.154.160.0/20 and 91.108.4.0/22. Most users won't need to do anything to continue receiving webhooks. If you control inbound access with a firewall, you may need to update your configuration. You can always find the list of actual IP addresses of servers used to send webhooks there: https://core.telegram.org/bots/webhooks.

- Document thumbnails now should be inscribed in a 320x320 square instead of 90x90.

### 2018

#### August 27, 2018

Bot API 4.1

- Added support for translated versions of documents in Telegram Passport.

- New field translation in EncryptedPassportElement.

- New errors: PassportElementErrorTranslationFile and PassportElementErrorTranslationFiles and PassportElementErrorUnspecified.

#### July 26, 2018

Bot API 4.0.

- Added support for Telegram Passport. See the official announcement on the blog and the manual for details.

- Added support for editing the media content of messages: added the method editMessageMedia and new types InputMediaAnimation, InputMediaAudio, and InputMediaDocument.

- Added the field thumb to the Audio object to contain the thumbnail of the album cover to which the music file belongs.

- Added support for attaching custom thumbnails to uploaded files. For animations, audios, videos and video notes, which are less than 10 MB in size, thumbnails are generated automatically.

- tg:// URLs now can be used in inline keyboard url buttons and text_link message entities.

- Added the method sendAnimation, which can be used instead of sendDocument to send animations, specifying their duration, width and height.

- Added the field animation to the Message object. For backward compatibility, when this field is set, the document field will be also set.

- Added two new MessageEntity types: cashtag and phone_number.

- Added support for Foursquare venues: added the new field foursquare_type to the objects Venue, InlineQueryResultVenue and InputVenueMessageContent, and the parameter foursquare_type to the sendVenue method.

- You can now create inline mentions of users, who have pressed your bot's callback buttons.

- You can now use the Retry-After response header to configure the delay after which the Bot API will retry the request after an unsuccessful response from a webhook.

- If a webhook returns the HTTP error 410 Gone for all requests for more than 23 hours successively, it can be automatically removed.

- Added vCard support when sharing contacts: added the field vcard to the objects Contact, InlineQueryResultContact, InputContactMessageContent and the method sendContact.

#### February 13, 2018

Bot API 3.6.

- Supported text formatting in media captions. Specify the desired parse_mode (Markdown or HTML) when you provide a caption.

- In supergroups, if the bot receives a message that is a reply, it will also receive the message to which that message is replying – even if the original message is inaccessible due to the bot's privacy settings. (In other words, replying to any message in a supergroup with a message that mentions the bot or features a command for it acts as forwarding the original message to the bot).

- Added the new field connected_website to Message. The bot will receive a message with this field in a private chat when a user logs in on the bot's connected website using the Login Widget and allows sending messages from your bot.

- Added the new parameter supports_streaming to the sendVideo method and a field with the same name to the InputMediaVideo object.

### 2017

#### November 17, 2017

Bot API 3.5.

- Added the new method sendMediaGroup and two kinds of InputMedia objects to support the new albums feature.

- Added support for pinning messages in channels. pinChatMessage and unpinChatMessage accept channels.

- Added the new fields provider_data, send_phone_number_to_provider, send_email_to_provider to sendInvoice for sharing information about the invoice with the payment provider.

#### October 11, 2017

Bot API 3.4.

- Bots can now send and receive Live Locations. Added new field live_period to the sendLocation method and the editMessageLiveLocation and stopMessageLiveLocation methods as well as the necessary objects for inline bots.

- Bots can use the new setChatStickerSet and deleteChatStickerSet methods to manage group sticker sets.

- The getChat request now returns the group's sticker set for supergroups if available.

- Bots now receive entities from media captions in the new field caption_entities in Message.

#### August 23, 2017

Bot API 3.3.

- Bots can now mention users via inline mentions, without using usernames.

- getChat now also returns pinned messages in supergroups, if present. Added the new field pinned_message to the Chat object.

- Added the new fields author_signature and forward_signature to the Message object.

- Added the new field is_bot to the User object.

#### July 21, 2017

Bot API 3.2. Teach your bot to handle stickers and sticker sets.

- Added new methods for working with stickers: getStickerSet, uploadStickerFile, createNewStickerSet, addStickerToSet, setStickerPositionInSet, and deleteStickerFromSet.

- Added the fields set_name and mask_position to the Sticker object, plus two new objects, StickerSet, and MaskPosition.

#### June 30, 2017

Bot API 3.1. Build your own robotic police force for supergoups with these new methods for admin bots:

- Added new methods restrictChatMember and promoteChatMember to manage users and admins, added new parameter until_date to kickChatMember for temporary bans.

- Added new methods exportChatInviteLink, setChatPhoto, deleteChatPhoto, setChatTitle, setChatDescription, pinChatMessage and unpinChatMessage to manage groups and channels.

- Added the new fields photo, description and invite_link to the Chat object.

- Added the new fields until_date, can_be_edited, can_change_info, can_post_messages, can_edit_messages, can_delete_messages, can_invite_users, can_restrict_members, can_pin_messages, can_promote_members, can_send_messages, can_send_media_messages, can_send_other_messages and can_add_web_page_previews to the ChatMember object.

#### May 18, 2017

Introducing Bot API 3.0.

NEW Payment Platform

See Introduction to Bot Payments for a brief overview. If you're not a developer, you may like this user-friendly blog post better.

- Your bot can now accept payments for goods and services via Telegram.

- Added new kinds of updates, shipping_query and pre_checkout_query, and new types of message content, invoice and successful_payment.

- Added new methods for payments: sendInvoice, answerShippingQuery, and answerPreCheckoutQuery.

- Added a new type of button, the pay button to InlineKeyboardButton.

NEW Video Messages

- As of Telegram v.4.0, users can send short rounded video messages, using an interface similar to that of voice notes.

- Added the sendVideoNote method, the new field video_note to Message, the fields record_video_note or upload_video_note to sendChatAction.

NEW Multilingual Bots

- The User object now may have a language_code field that contains the IETF language tag of the user's language.

- Thanks to this, your bot can now offer localized responses to users that speak different languages.

More power to admin bots

- unbanChatMemeber now also works in channels!

- New method deleteMessage that allows the bot to delete its own messages, as well as messages posted by other in groups and channels where the bot is an administrator.

Minor Changes

- Replaced the field new_chat_member in Message with new_chat_members (the old field will still be available for a while for compatibility purposes).

- Inline keyboards with switch_inline_query and switch_inline_query_current_chat can no longer be sent to channels because they are useless there.

- New fields gif_duration in InlineQueryResultGif and mpeg4_duration in InlineQueryResultMpeg4Gif.

### 2016

#### December 4, 2016

Introducing Bot API 2.3.1, a nifty little update that will give you more control over how your bot gets its updates.

- Use the new field max_connections in setWebhook to optimize your bot's server load

- Use allowed_updates in setWebhook and getUpdates to selectively subscribe to updates of a certain type. Among other things, this allows you to stop getting updates about new posts in channels where your bot is an admin.

- deleteWebhook moved out of setWebhook to get a whole separate method for itself.

#### November 21, 2016

Bot API 2.3

- Modified bot privacy mode for the sake of consistency.

- Your bot can now get updates about posts in channels. Added new fields channel_post and edited_channel_post to Update.

- You can now update high scores to a lower value by using the new force parameter in setGameScore. Handy for punishing cheaters or fixing errors in your game's High Score table.

- Starting today, messages with high scores will be updated with new high scores by default. Use disable_edit_message in setGameScore if you don't want this.

- The edit_message parameter from setGameScore is no longer in use. For backward compatibility, it will be taken into account for a while, unless disable_edit_message is passed explicitly.

- Added the new field forward_from_message_id to Message.

- Added the new parameter cache_time to answerCallbackQuery. Will eventually work in Telegram apps — somewhere after version 3.14, maybe 3.15.

- Renamed hide_keyboard to remove_keyboard in ReplyKeyboardRemove for clarity. hide_keyboard will still work for a while for backward compatibility.

#### October 3, 2016

Bot API 2.2. Introducing a new Gaming Platform! See this introduction for a brief overview.
If you're not a developer, you may like this user-friendly blog post better.

- New tools for building HTML5 games.

- New method sendGame, new object InlineQueryResultGame, new field game in Message.

- New parameter url in answerCallbackQuery. Create a game and accept the conditions using Botfather to send custom urls that open your games for the user.

- New field callback_game in InlineKeyboardButton, new fields game_short_name and chat_instance in CallbackQuery, new object CallbackGame.

- New methods setGameScore and getGameHighScores.

Other changes

- Making life easier for webhook users. Added a detailed Guide to All Things Webhook that describes every pothole you can run into on the webhook road.

- New method getWebhookInfo to check current webhook status.

- Added the option to specify an HTTP URL for a file in all methods where InputFile or file_id can be used (except voice messages). Telegram will get the file from the specified URL and send it to the user. Files must be smaller than 5 MB for photos and smaller than 20 MB for all other types of content.

- Use the new url parameter in answerCallbackQuery to create buttons that open your bot with user-specific parameters.

- Added new field switch_inline_query_current_chat in InlineKeyboardButton.

- Added caption fields to sendAudio, sendVoice, InlineQueryResultAudio, InlineQueryResultVoice, InlineQueryResultCachedAudio, and InlineQueryResultCachedVoice.

- New field all_members_are_administrators in the Chat object.

- Certain server responses may now contain the new parameters field with expanded info on errors that occurred while processing your requests.

#### May 25, 2016

- Inline keyboards may now be used in group chats. Channels coming soon.

- Check out @vote and @like for examples.

#### May 22, 2016

- Bot API 2.1. Added more tools for group administrator bots. Your bot can now get a list of administrators and members count in a group, check a user's current status (administrator, creator, left the group, kicked from the group), and leave a group.

- Added new methods: getChat, leaveChat, getChatAdministrators, getChatMember, getChatMembersCount.

- Added support for edited messages and new mentions from Telegram v.3.9. New fields: edited_message in Update, edit_date in Message, user in MessageEntity. New value text_mention for the type field in MessageEntity.

#### May 12, 2016

- Added consistency to what messages bots get in groups and supergroups. See updated FAQ for details »

#### May 6, 2016

- Added the field emoji to the Sticker object. Your bot can now know the emoji a sticker corresponds to.

- Added the field forward_from_chat to the Message object for messages forwarded from channels.

#### April 9, 2016

Introducing Bot API 2.0. Check out this page for a review of this major update.

- New inline keyboards with callback and URL buttons. Added new objects InlineKeyboardMarkup, InlineKeyboardButton and CallbackQuery, added reply_markup fields to all InlineQueryResult objects. Added field callback_query to the Update object, new method answerCallbackQuery.

- Bots can now edit their messages. Added methods editMessageText, editMessageCaption, editMessageReplyMarkup.

- Bots can request location and phone number from the user. The keyboard field in the object ReplyKeyboardMarkup now supports KeyboardButton, a new object that can have the fields request_location and request_contact.

Inline bots

- Added support for all content types available on Telegram. 19 types of InlineQueryResult objects are now supported.

- Inline bots can now substitute all kinds of content with text. Added 4 types of InputMessageContent objects.

- Your inline bot can also ask users for permission to use their location. Added the new Botfather command /setinlinegeo, added field location to the InlineQuery object, added fields location and inline_message_id to the ChosenInlineResult object.

- Added an easy way to switch between inline mode and a private chat with the bot – useful for settings, establishing external connections and teaching users how to use your bot in inline mode. Added parameters switch_pm_text and switch_pm_parameter to the method answerInlineQuery.

Miscellaneous

- Added group administration tools. New methods kickChatMember and unbanChatMember.

- Added fields venue, pinned_message and entities to the Message object. Added new objects MessageEntity and Venue, new methods sendVenue and sendContact.

- Renamed the fields new_chat_participant and left_chat_participant of the Message object to new_chat_member and left_chat_member.

#### February 20, 2016

- Added the disable_notification parameter to all methods that send messages or any kind.

- Removed backward compatibility from the method sendAudio. Voice messages now must be sent using the method sendVoice. There is no more need to specify a non-empty title or performer while sending the audio by file_id.

#### January 20, 2016

- By the way, you can use both HTML-style and markdown-style formatting in your bot's messages to send bold, italic or fixed-width text and inline links. All official Telegram clients support this. See Formatting options for details.

#### January 14, 2016

- You can now collect feedback on which results provided by your inline bot get chosen by the users. Added the setinlinefeedback command for Botfather, new type ChosenInlineResult, new field chosen_inline_result to the Update object.

#### January 4, 2016

- Added support for Inline Mode, a new way for people to contact your bot by typing its username and a query in the text input field in any chat. Enable by sending /setinline to @BotFather.

- New optional field inline_query added to the Update object.

- Added new method answerInlineQuery and new objects InlineQuery, InlineQueryResultArticle, InlineQueryResultPhoto, InlineQueryResultGif, InlineQueryResultMpeg4Gif and InlineQueryResultVideo.

### 2015

#### November, 2015

- Added support for supergroups. The Type field in the Chat object can now contain 'supergroup'.

- New optional fields added to the Message object: supergroup_chat_created, migrate_to_chat_id, migrate_from_chat_id and channel_chat_created.

#### October 8, 2015

- Added initial channel support for bots (no Telegram clients support this at the moment, please wait for updates):

- The Chat field in the Message is now of the new type Chat.

- You can now pass a channel username (in the format @channelusername) in the place of chat_id in all methods (and instead of from_chat_id in forwardMessage). For this to work, the bot must be an administrator in the channel (and that's exactly what Telegram clients don't support yet — adding bots as administrators coming soon).

#### September 18, 2015

- Bots can now download files and media sent by users.

- Added getFile and File.

#### September 7, 2015

- You can now pass parameters using application/json (please note that this doesn't work for file uploads: use multipart/form-data to upload files).

- Added very basic markdown support. New field parse_mode added to sendMessage. For the moment messages with markdown will be displayed correctly only in Telegram for Android. Other official apps will catch up soon.

#### August 29, 2015

- Added support for self-signed certificates: upload your certificate using the certificate parameter in the setWebhook method.

- You can now make new requests when responding to webhook updates.

#### August 15, 2015

- Added new type Voice and new method sendVoice for sending voice messages.

- Earlier Audio and sendAudio should now be used for sending music files. Telegram clients will show such files in the in-app music player. If you were using sendAudio for your bot to send voice messages, please use sendVoice instead.

- Added optional fields performer, title to the Audio object and sendAudio method.

- Added optional field voice to the Message object.

#### July 2015

- The thumb field is now optional for Video, Sticker and Document objects

- The API now supports both video and photo captions. The caption field has been removed from the Video object and added to the Message object instead.

- caption and duration optional fields have been added to the sendVideo method.

- Fixed typo: user_id in the Contact object is now correctly labeled as Integer, not String

#### June 24, 2015

The bot platform is officially launched.

> Back to the Bot API Manual »

