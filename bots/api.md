# Telegram Bot API

> The Bot API is an HTTP-based interface created for developers keen on building bots for Telegram.To learn how to create and set up a bot, please consult our Introduction to Bots and Bot FAQ.

### Recent changes

> Subscribe to @BotNews to be the first to know about the latest updates and join the discussion in @BotTalk

#### December 31, 2025

Bot API 9.3

Topics in private chats

- Added the field has_topics_enabled to the class User, which can be used to determine whether forum topic mode is enabled for the bot in private chats.

- Added the method sendMessageDraft, allowing partial messages to be streamed to a user while being generated.

- Supported the fields message_thread_id and is_topic_message in the class Message for messages in private chats with forum topic mode enabled.

- Supported the parameter message_thread_id in private chats with topics in the methods sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendPaidMedia, sendSticker, sendVideoNote, sendVoice, sendLocation, sendVenue, sendContact, sendPoll, sendDice, sendInvoice, sendGame, sendMediaGroup, copyMessage, copyMessages, forwardMessage, and forwardMessages, allowing bots to send a message to a specific topic.

- Supported the parameter message_thread_id in private chats in the method sendChatAction, allowing bots to send chat actions to a specific topic in private chats.

- Supported the parameter message_thread_id in private chats with topics in the method editForumTopic, deleteForumTopic, and unpinAllForumTopicMessages, allowing bots to manage topics in private chats.

- Added the field is_name_implicit to the classes ForumTopic and ForumTopicCreated.

Gifts

- Added the methods getUserGifts and getChatGifts.

- Replaced the field last_resale_star_count with the fields last_resale_currency and last_resale_amount in the class UniqueGiftInfo.

- Replaced the parameter exclude_limited with the parameters exclude_limited_upgradable and exclude_limited_non_upgradable in the method getBusinessAccountGifts.

- Added the value “gifted_upgrade” as a possible value of UniqueGiftInfo.origin for messages about the upgrade of a gift that was purchased after it was sent.

- Added the value “offer” as a possible value of UniqueGiftInfo.origin for messages about the purchase of a gift through a purchase offer.

- Added the field gift_upgrade_sent to the class Message.

- Added the field gift_id to the class UniqueGift.

- Added the field is_from_blockchain to the class UniqueGift.

- Added the parameter exclude_from_blockchain in the method getBusinessAccountGifts, to filter out gifts that were assigned from the TON blockchain.

- Added the fields personal_total_count and personal_remaining_count to the class Gift.

- Added the field is_premium to the classes Gift and UniqueGift.

- Added the field is_upgrade_separate to the classes GiftInfo and OwnedGiftRegular.

- Added the class UniqueGiftColors that describes the color scheme for a user's name, replies to messages and link previews based on a unique gift.

- Added the field has_colors to the class Gift.

- Added the field colors to the class UniqueGift.

- Added the class GiftBackground and the field background to the class Gift.

- Added the field unique_gift_variant_count to the class Gift.

- Added the field unique_gift_number to the classes GiftInfo and OwnedGiftRegular.

- Added the field gifts_from_channels to the class AcceptedGiftTypes.

Miscellaneous

- Allowed bots to disable their main username if they have additional active usernames purchased on Fragment.

- Allowed bots to disable the right can_restrict_members in channel chats.

- Added the method repostStory, allowing bots to repost stories across different business accounts they manage.

- Added the class UserRating and the field rating to the class ChatFullInfo.

- Increased the maximum price for paid media to 25000 Telegram Stars.

- Added the field paid_message_star_count to the class ChatFullInfo.

- Added the parameter message_effect_id to the methods forwardMessage and copyMessage.

- Added the field unique_gift_colors to the class ChatFullInfo.

- Added the field completed_by_chat to the class ChecklistTask.

#### August 15, 2025

Bot API 9.2

Checklists

- Added the field checklist_task_id to the class ReplyParameters, allowing bots to reply to a specific checklist task.

- Added the field reply_to_checklist_task_id to the class Message.

Gifts

- Added the field publisher_chat to the classes Gift and UniqueGift which can be used to get information about the chat that published a gift.

Direct Messages in Channels

- Added the field is_direct_messages to the classes Chat and ChatFullInfo which can be used to identify supergroups that are used as channel direct messages chats.

- Added the field parent_chat to the class ChatFullInfo which indicates the parent channel chat for a channel direct messages chat.

- Added the class DirectMessagesTopic and the field direct_messages_topic to the class Message, describing a topic of a direct messages chat.

- Added the parameter direct_messages_topic_id to the methods sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendPaidMedia, sendSticker, sendVideoNote, sendVoice, sendLocation, sendVenue, sendContact, sendDice, sendInvoice, sendMediaGroup, copyMessage, copyMessages, forwardMessage and forwardMessages. This parameter can be used to send a message to a direct messages chat topic.

Suggested Posts

- Added the class SuggestedPostParameters and the parameter suggested_post_parameters to the methods sendMessage, sendPhoto, sendVideo, sendAnimation, sendAudio, sendDocument, sendPaidMedia, sendSticker, sendVideoNote, sendVoice, sendLocation, sendVenue, sendContact, sendDice, sendInvoice, copyMessage, forwardMessage. This parameter can be used to send a suggested post to a direct messages chat topic.

- Added the method approveSuggestedPost, allowing bots to approve incoming suggested posts.

- Added the method declineSuggestedPost, allowing bots to decline incoming suggested posts.

- Added the field can_manage_direct_messages to the classes ChatMemberAdministrator and ChatAdministratorRights.

- Added the parameter can_manage_direct_messages to the method promoteChatMember.

- Added the field is_paid_post to the class Message, which can be used to identify paid posts. Such posts must not be deleted for 24 hours to receive the payment.

- Added the class SuggestedPostPrice, describing the price of a suggested post.

- Added the class SuggestedPostInfo and the field suggested_post_info to the class Message, describing a suggested post.

- Added the class SuggestedPostApproved and the field suggested_post_approved to the class Message, describing a service message about the approval of a suggested post.

- Added the class SuggestedPostApprovalFailed and the field suggested_post_approval_failed to the class Message, describing a service message about the failed approval of a suggested post.

- Added the class SuggestedPostDeclined and the field suggested_post_declined to the class Message, describing a service message about the rejection of a suggested post.

- Added the class SuggestedPostPaid and the field suggested_post_paid to the class Message, describing a service message about a successful payment for a suggested post.

- Added the class SuggestedPostRefunded and the field suggested_post_refunded to the class Message, describing a service message about a payment refund for a suggested post.

#### July 3, 2025

Bot API 9.1

Checklists

- Added the class ChecklistTask representing a task in a checklist.

- Added the class Checklist representing a checklist.

- Added the class InputChecklistTask representing a task to add to a checklist.

- Added the class InputChecklist representing a checklist to create.

- Added the field checklist to the classes Message and ExternalReplyInfo, describing a checklist in a message.

- Added the class ChecklistTasksDone and the field checklist_tasks_done to the class Message, describing a service message about status changes for tasks in a checklist (i.e., marked as done/not done).

- Added the class ChecklistTasksAdded and the field checklist_tasks_added to the class Message, describing a service message about the addition of new tasks to a checklist.

- Added the method sendChecklist, allowing bots to send a checklist on behalf of a business account.

- Added the method editMessageChecklist, allowing bots to edit a checklist on behalf of a business account.

Gifts

- Added the field next_transfer_date to the classes OwnedGiftUnique and UniqueGiftInfo.

- Added the field last_resale_star_count to the class UniqueGiftInfo.

- Added “resale” as the possible value of the field origin in the class UniqueGiftInfo.

General

- Increased the maximum number of options in a poll to 12.

- Added the method getMyStarBalance, allowing bots to get their current balance of Telegram Stars.

- Added the class DirectMessagePriceChanged and the field direct_message_price_changed to the class Message, describing a service message about a price change for direct messages sent to the channel chat.

- Added the method hideKeyboard to the class WebApp.

See earlier changes »

### Authorizing your bot

Each bot is given a unique authentication token when it is created. The token looks something like 123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11, but we'll use simply <token> in this document instead. You can learn about obtaining tokens and generating new ones in this document.

### Making requests

All queries to the Telegram Bot API must be served over HTTPS and need to be presented in this form: https://api.telegram.org/bot<token>/METHOD_NAME. Like this for example:

```
https://api.telegram.org/bot123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11/getMe
```

We support GET and POST HTTP methods. We support four ways of passing parameters in Bot API requests:

- URL query string

- application/x-www-form-urlencoded

- application/json (except for uploading files)

- multipart/form-data (use to upload files)

The response contains a JSON object, which always has a Boolean field 'ok' and may have an optional String field 'description' with a human-readable description of the result. If 'ok' equals True, the request was successful and the result of the query can be found in the 'result' field. In case of an unsuccessful request, 'ok' equals false and the error is explained in the 'description'. An Integer 'error_code' field is also returned, but its contents are subject to change in the future. Some errors may also have an optional field 'parameters' of the type ResponseParameters, which can help to automatically handle the error.

- All methods in the Bot API are case-insensitive.

- All queries must be made using UTF-8.

#### Making requests when getting updates

If you're using webhooks, you can perform a request to the Bot API while sending an answer to the webhook. Use either application/json or application/x-www-form-urlencoded or multipart/form-data response content type for passing parameters. Specify the method to be invoked in the method parameter of the request. It's not possible to know that such a request was successful or get its result.

> Please see our FAQ for examples.

### Using a Local Bot API Server

The Bot API server source code is available at telegram-bot-api. You can run it locally and send the requests to your own server instead of https://api.telegram.org. If you switch to a local Bot API server, your bot will be able to:

- Download files without a size limit.

- Upload files up to 2000 MB.

- Upload files using their local path and the file URI scheme.

- Use an HTTP URL for the webhook.

- Use any local IP address for the webhook.

- Use any port for the webhook.

- Set max_webhook_connections up to 100000.

- Receive the absolute local path as a value of the file_path field without the need to download the file after a getFile request.

#### Do I need a Local Bot API Server

The majority of bots will be OK with the default configuration, running on our servers. But if you feel that you need one of these features, you're welcome to switch to your own at any time.

### Getting updates

There are two mutually exclusive ways of receiving updates for your bot - the getUpdates method on one hand and webhooks on the other. Incoming updates are stored on the server until the bot receives them either way, but they will not be kept longer than 24 hours.

Regardless of which option you choose, you will receive JSON-serialized Update objects as a result.

#### Update

This object represents an incoming update.At most one of the optional parameters can be present in any given update.

#### getUpdates

Use this method to receive incoming updates using long polling (wiki). Returns an Array of Update objects.

> Notes1. This method will not work if an outgoing webhook is set up.2. In order to avoid getting duplicate updates, recalculate offset after each server response.

#### setWebhook

Use this method to specify a URL and receive incoming updates via an outgoing webhook. Whenever there is an update for the bot, we will send an HTTPS POST request to the specified URL, containing a JSON-serialized Update. In case of an unsuccessful request (a request with response HTTP status code different from 2XY), we will repeat the request and give up after a reasonable amount of attempts. Returns True on success.

If you'd like to make sure that the webhook was set by you, you can specify secret data in the parameter secret_token. If specified, the request will contain a header “X-Telegram-Bot-Api-Secret-Token” with the secret token as content.

> Notes1. You will not be able to receive updates using getUpdates for as long as an outgoing webhook is set up.2. To use a self-signed certificate, you need to upload your public key certificate using certificate parameter. Please upload as InputFile, sending a String will not work.3. Ports currently supported for webhooks: 443, 80, 88, 8443.
If you're having any trouble setting up webhooks, please check out this amazing guide to webhooks.

#### deleteWebhook

Use this method to remove webhook integration if you decide to switch back to getUpdates. Returns True on success.

#### getWebhookInfo

Use this method to get current webhook status. Requires no parameters. On success, returns a WebhookInfo object. If the bot is using getUpdates, will return an object with the url field empty.

#### WebhookInfo

Describes the current status of a webhook.

### Available types

All types used in the Bot API responses are represented as JSON-objects.

It is safe to use 32-bit signed integers for storing all Integer fields unless otherwise noted.

> Optional fields may be not returned when irrelevant.

#### User

This object represents a Telegram user or bot.

#### Chat

This object represents a chat.

#### ChatFullInfo

This object contains full information about a chat.

#### Message

This object represents a message.

#### MessageId

This object represents a unique message identifier.

#### InaccessibleMessage

This object describes a message that was deleted or is otherwise inaccessible to the bot.

#### MaybeInaccessibleMessage

This object describes a message that can be inaccessible to the bot. It can be one of

- Message

- InaccessibleMessage

#### MessageEntity

This object represents one special entity in a text message. For example, hashtags, usernames, URLs, etc.

#### TextQuote

This object contains information about the quoted part of a message that is replied to by the given message.

#### ExternalReplyInfo

This object contains information about a message that is being replied to, which may come from another chat or forum topic.

#### ReplyParameters

Describes reply parameters for the message that is being sent.

#### MessageOrigin

This object describes the origin of a message. It can be one of

- MessageOriginUser

- MessageOriginHiddenUser

- MessageOriginChat

- MessageOriginChannel

#### MessageOriginUser

The message was originally sent by a known user.

#### MessageOriginHiddenUser

The message was originally sent by an unknown user.

#### MessageOriginChat

The message was originally sent on behalf of a chat to a group chat.

#### MessageOriginChannel

The message was originally sent to a channel chat.

#### PhotoSize

This object represents one size of a photo or a file / sticker thumbnail.

#### Animation

This object represents an animation file (GIF or H.264/MPEG-4 AVC video without sound).

#### Audio

This object represents an audio file to be treated as music by the Telegram clients.

#### Document

This object represents a general file (as opposed to photos, voice messages and audio files).

#### Story

This object represents a story.

#### Video

This object represents a video file.

#### VideoNote

This object represents a video message (available in Telegram apps as of v.4.0).

#### Voice

This object represents a voice note.

#### PaidMediaInfo

Describes the paid media added to a message.

#### PaidMedia

This object describes paid media. Currently, it can be one of

- PaidMediaPreview

- PaidMediaPhoto

- PaidMediaVideo

#### PaidMediaPreview

The paid media isn't available before the payment.

#### PaidMediaPhoto

The paid media is a photo.

#### PaidMediaVideo

The paid media is a video.

#### Contact

This object represents a phone contact.

#### Dice

This object represents an animated emoji that displays a random value.

#### PollOption

This object contains information about one answer option in a poll.

#### InputPollOption

This object contains information about one answer option in a poll to be sent.

#### PollAnswer

This object represents an answer of a user in a non-anonymous poll.

#### Poll

This object contains information about a poll.

#### ChecklistTask

Describes a task in a checklist.

#### Checklist

Describes a checklist.

#### InputChecklistTask

Describes a task to add to a checklist.

#### InputChecklist

Describes a checklist to create.

#### ChecklistTasksDone

Describes a service message about checklist tasks marked as done or not done.

#### ChecklistTasksAdded

Describes a service message about tasks added to a checklist.

#### Location

This object represents a point on the map.

#### Venue

This object represents a venue.

#### WebAppData

Describes data sent from a Web App to the bot.

#### ProximityAlertTriggered

This object represents the content of a service message, sent whenever a user in the chat triggers a proximity alert set by another user.

#### MessageAutoDeleteTimerChanged

This object represents a service message about a change in auto-delete timer settings.

#### ChatBoostAdded

This object represents a service message about a user boosting a chat.

#### BackgroundFill

This object describes the way a background is filled based on the selected colors. Currently, it can be one of

- BackgroundFillSolid

- BackgroundFillGradient

- BackgroundFillFreeformGradient

#### BackgroundFillSolid

The background is filled using the selected color.

#### BackgroundFillGradient

The background is a gradient fill.

#### BackgroundFillFreeformGradient

The background is a freeform gradient that rotates after every message in the chat.

#### BackgroundType

This object describes the type of a background. Currently, it can be one of

- BackgroundTypeFill

- BackgroundTypeWallpaper

- BackgroundTypePattern

- BackgroundTypeChatTheme

#### BackgroundTypeFill

The background is automatically filled based on the selected colors.

#### BackgroundTypeWallpaper

The background is a wallpaper in the JPEG format.

#### BackgroundTypePattern

The background is a .PNG or .TGV (gzipped subset of SVG with MIME type “application/x-tgwallpattern”) pattern to be combined with the background fill chosen by the user.

#### BackgroundTypeChatTheme

The background is taken directly from a built-in chat theme.

#### ChatBackground

This object represents a chat background.

#### ForumTopicCreated

This object represents a service message about a new forum topic created in the chat.

#### ForumTopicClosed

This object represents a service message about a forum topic closed in the chat. Currently holds no information.

#### ForumTopicEdited

This object represents a service message about an edited forum topic.

#### ForumTopicReopened

This object represents a service message about a forum topic reopened in the chat. Currently holds no information.

#### GeneralForumTopicHidden

This object represents a service message about General forum topic hidden in the chat. Currently holds no information.

#### GeneralForumTopicUnhidden

This object represents a service message about General forum topic unhidden in the chat. Currently holds no information.

#### SharedUser

This object contains information about a user that was shared with the bot using a KeyboardButtonRequestUsers button.

#### UsersShared

This object contains information about the users whose identifiers were shared with the bot using a KeyboardButtonRequestUsers button.

#### ChatShared

This object contains information about a chat that was shared with the bot using a KeyboardButtonRequestChat button.

#### WriteAccessAllowed

This object represents a service message about a user allowing a bot to write messages after adding it to the attachment menu, launching a Web App from a link, or accepting an explicit request from a Web App sent by the method requestWriteAccess.

#### VideoChatScheduled

This object represents a service message about a video chat scheduled in the chat.

#### VideoChatStarted

This object represents a service message about a video chat started in the chat. Currently holds no information.

#### VideoChatEnded

This object represents a service message about a video chat ended in the chat.

#### VideoChatParticipantsInvited

This object represents a service message about new members invited to a video chat.

#### PaidMessagePriceChanged

Describes a service message about a change in the price of paid messages within a chat.

#### DirectMessagePriceChanged

Describes a service message about a change in the price of direct messages sent to a channel chat.

#### SuggestedPostApproved

Describes a service message about the approval of a suggested post.

#### SuggestedPostApprovalFailed

Describes a service message about the failed approval of a suggested post. Currently, only caused by insufficient user funds at the time of approval.

#### SuggestedPostDeclined

Describes a service message about the rejection of a suggested post.

#### SuggestedPostPaid

Describes a service message about a successful payment for a suggested post.

#### SuggestedPostRefunded

Describes a service message about a payment refund for a suggested post.

#### GiveawayCreated

This object represents a service message about the creation of a scheduled giveaway.

#### Giveaway

This object represents a message about a scheduled giveaway.

#### GiveawayWinners

This object represents a message about the completion of a giveaway with public winners.

#### GiveawayCompleted

This object represents a service message about the completion of a giveaway without public winners.

#### LinkPreviewOptions

Describes the options used for link preview generation.

#### SuggestedPostPrice

Describes the price of a suggested post.

#### SuggestedPostInfo

Contains information about a suggested post.

#### SuggestedPostParameters

Contains parameters of a post that is being suggested by the bot.

#### DirectMessagesTopic

Describes a topic of a direct messages chat.

#### UserProfilePhotos

This object represent a user's profile pictures.

#### File

This object represents a file ready to be downloaded. The file can be downloaded via the link https://api.telegram.org/file/bot<token>/<file_path>. It is guaranteed that the link will be valid for at least 1 hour. When the link expires, a new one can be requested by calling getFile.

> The maximum file size to download is 20 MB

#### WebAppInfo

Describes a Web App.

#### ReplyKeyboardMarkup

This object represents a custom keyboard with reply options (see Introduction to bots for details and examples). Not supported in channels and for messages sent on behalf of a Telegram Business account.

#### KeyboardButton

This object represents one button of the reply keyboard. At most one of the optional fields must be used to specify type of the button. For simple text buttons, String can be used instead of this object to specify the button text.

Note: request_users and request_chat options will only work in Telegram versions released after 3 February, 2023. Older clients will display unsupported message.

#### KeyboardButtonRequestUsers

This object defines the criteria used to request suitable users. Information about the selected users will be shared with the bot when the corresponding button is pressed. More about requesting users »

#### KeyboardButtonRequestChat

This object defines the criteria used to request a suitable chat. Information about the selected chat will be shared with the bot when the corresponding button is pressed. The bot will be granted requested rights in the chat if appropriate. More about requesting chats ».

#### KeyboardButtonPollType

This object represents type of a poll, which is allowed to be created and sent when the corresponding button is pressed.

#### ReplyKeyboardRemove

Upon receiving a message with this object, Telegram clients will remove the current custom keyboard and display the default letter-keyboard. By default, custom keyboards are displayed until a new keyboard is sent by a bot. An exception is made for one-time keyboards that are hidden immediately after the user presses a button (see ReplyKeyboardMarkup). Not supported in channels and for messages sent on behalf of a Telegram Business account.

#### InlineKeyboardMarkup

This object represents an inline keyboard that appears right next to the message it belongs to.

#### InlineKeyboardButton

This object represents one button of an inline keyboard. Exactly one of the optional fields must be used to specify type of the button.

#### LoginUrl

This object represents a parameter of the inline keyboard button used to automatically authorize a user. Serves as a great replacement for the Telegram Login Widget when the user is coming from Telegram. All the user needs to do is tap/click a button and confirm that they want to log in:

Telegram apps support these buttons as of version 5.7.

> Sample bot: @discussbot

#### SwitchInlineQueryChosenChat

This object represents an inline button that switches the current user to inline mode in a chosen chat, with an optional default inline query.

#### CopyTextButton

This object represents an inline keyboard button that copies specified text to the clipboard.

#### CallbackQuery

This object represents an incoming callback query from a callback button in an inline keyboard. If the button that originated the query was attached to a message sent by the bot, the field message will be present. If the button was attached to a message sent via the bot (in inline mode), the field inline_message_id will be present. Exactly one of the fields data or game_short_name will be present.

> NOTE: After the user presses a callback button, Telegram clients will display a progress bar until you call answerCallbackQuery. It is, therefore, necessary to react by calling answerCallbackQuery even if no notification to the user is needed (e.g., without specifying any of the optional parameters).

#### ForceReply

Upon receiving a message with this object, Telegram clients will display a reply interface to the user (act as if the user has selected the bot's message and tapped 'Reply'). This can be extremely useful if you want to create user-friendly step-by-step interfaces without having to sacrifice privacy mode. Not supported in channels and for messages sent on behalf of a Telegram Business account.

> Example: A poll bot for groups runs in privacy mode (only receives commands, replies to its messages and mentions). There could be two ways to create a new poll:

Explain the user how to send a command with parameters (e.g. /newpoll question answer1 answer2). May be appealing for hardcore users but lacks modern day polish.
Guide the user through a step-by-step process. 'Please send me your question', 'Cool, now let's add the first answer option', 'Great. Keep adding answer options, then send /done when you're ready'.

The last option is definitely more attractive. And if you use ForceReply in your bot's questions, it will receive the user's answers even if it only receives replies, commands and mentions - without any extra work for the user.

#### ChatPhoto

This object represents a chat photo.

#### ChatInviteLink

Represents an invite link for a chat.

#### ChatAdministratorRights

Represents the rights of an administrator in a chat.

#### ChatMemberUpdated

This object represents changes in the status of a chat member.

#### ChatMember

This object contains information about one member of a chat. Currently, the following 6 types of chat members are supported:

- ChatMemberOwner

- ChatMemberAdministrator

- ChatMemberMember

- ChatMemberRestricted

- ChatMemberLeft

- ChatMemberBanned

#### ChatMemberOwner

Represents a chat member that owns the chat and has all administrator privileges.

#### ChatMemberAdministrator

Represents a chat member that has some additional privileges.

#### ChatMemberMember

Represents a chat member that has no additional privileges or restrictions.

#### ChatMemberRestricted

Represents a chat member that is under certain restrictions in the chat. Supergroups only.

#### ChatMemberLeft

Represents a chat member that isn't currently a member of the chat, but may join it themselves.

#### ChatMemberBanned

Represents a chat member that was banned in the chat and can't return to the chat or view chat messages.

#### ChatJoinRequest

Represents a join request sent to a chat.

#### ChatPermissions

Describes actions that a non-administrator user is allowed to take in a chat.

#### Birthdate

Describes the birthdate of a user.

#### BusinessIntro

Contains information about the start page settings of a Telegram Business account.

#### BusinessLocation

Contains information about the location of a Telegram Business account.

#### BusinessOpeningHoursInterval

Describes an interval of time during which a business is open.

#### BusinessOpeningHours

Describes the opening hours of a business.

#### UserRating

This object describes the rating of a user based on their Telegram Star spendings.

#### StoryAreaPosition

Describes the position of a clickable area within a story.

#### LocationAddress

Describes the physical address of a location.

#### StoryAreaType

Describes the type of a clickable area on a story. Currently, it can be one of

- StoryAreaTypeLocation

- StoryAreaTypeSuggestedReaction

- StoryAreaTypeLink

- StoryAreaTypeWeather

- StoryAreaTypeUniqueGift

#### StoryAreaTypeLocation

Describes a story area pointing to a location. Currently, a story can have up to 10 location areas.

#### StoryAreaTypeSuggestedReaction

Describes a story area pointing to a suggested reaction. Currently, a story can have up to 5 suggested reaction areas.

#### StoryAreaTypeLink

Describes a story area pointing to an HTTP or tg:// link. Currently, a story can have up to 3 link areas.

#### StoryAreaTypeWeather

Describes a story area containing weather information. Currently, a story can have up to 3 weather areas.

#### StoryAreaTypeUniqueGift

Describes a story area pointing to a unique gift. Currently, a story can have at most 1 unique gift area.

#### StoryArea

Describes a clickable area on a story media.

#### ChatLocation

Represents a location to which a chat is connected.

#### ReactionType

This object describes the type of a reaction. Currently, it can be one of

- ReactionTypeEmoji

- ReactionTypeCustomEmoji

- ReactionTypePaid

#### ReactionTypeEmoji

The reaction is based on an emoji.

#### ReactionTypeCustomEmoji

The reaction is based on a custom emoji.

#### ReactionTypePaid

The reaction is paid.

#### ReactionCount

Represents a reaction added to a message along with the number of times it was added.

#### MessageReactionUpdated

This object represents a change of a reaction on a message performed by a user.

#### MessageReactionCountUpdated

This object represents reaction changes on a message with anonymous reactions.

#### ForumTopic

This object represents a forum topic.

#### GiftBackground

This object describes the background of a gift.

#### Gift

This object represents a gift that can be sent by the bot.

#### Gifts

This object represent a list of gifts.

#### UniqueGiftModel

This object describes the model of a unique gift.

#### UniqueGiftSymbol

This object describes the symbol shown on the pattern of a unique gift.

#### UniqueGiftBackdropColors

This object describes the colors of the backdrop of a unique gift.

#### UniqueGiftBackdrop

This object describes the backdrop of a unique gift.

#### UniqueGiftColors

This object contains information about the color scheme for a user's name, message replies and link previews based on a unique gift.

#### UniqueGift

This object describes a unique gift that was upgraded from a regular gift.

#### GiftInfo

Describes a service message about a regular gift that was sent or received.

#### UniqueGiftInfo

Describes a service message about a unique gift that was sent or received.

#### OwnedGift

This object describes a gift received and owned by a user or a chat. Currently, it can be one of

- OwnedGiftRegular

- OwnedGiftUnique

#### OwnedGiftRegular

Describes a regular gift owned by a user or a chat.

#### OwnedGiftUnique

Describes a unique gift received and owned by a user or a chat.

#### OwnedGifts

Contains the list of gifts received and owned by a user or a chat.

#### AcceptedGiftTypes

This object describes the types of gifts that can be gifted to a user or a chat.

#### StarAmount

Describes an amount of Telegram Stars.

#### BotCommand

This object represents a bot command.

#### BotCommandScope

This object represents the scope to which bot commands are applied. Currently, the following 7 scopes are supported:

- BotCommandScopeDefault

- BotCommandScopeAllPrivateChats

- BotCommandScopeAllGroupChats

- BotCommandScopeAllChatAdministrators

- BotCommandScopeChat

- BotCommandScopeChatAdministrators

- BotCommandScopeChatMember

#### Determining list of commands

The following algorithm is used to determine the list of commands for a particular user viewing the bot menu. The first list of commands which is set is returned:

Commands in the chat with the bot

- botCommandScopeChat + language_code

- botCommandScopeChat

- botCommandScopeAllPrivateChats + language_code

- botCommandScopeAllPrivateChats

- botCommandScopeDefault + language_code

- botCommandScopeDefault

Commands in group and supergroup chats

- botCommandScopeChatMember + language_code

- botCommandScopeChatMember

- botCommandScopeChatAdministrators + language_code (administrators only)

- botCommandScopeChatAdministrators (administrators only)

- botCommandScopeChat + language_code

- botCommandScopeChat

- botCommandScopeAllChatAdministrators + language_code (administrators only)

- botCommandScopeAllChatAdministrators (administrators only)

- botCommandScopeAllGroupChats + language_code

- botCommandScopeAllGroupChats

- botCommandScopeDefault + language_code

- botCommandScopeDefault

#### BotCommandScopeDefault

Represents the default scope of bot commands. Default commands are used if no commands with a narrower scope are specified for the user.

#### BotCommandScopeAllPrivateChats

Represents the scope of bot commands, covering all private chats.

#### BotCommandScopeAllGroupChats

Represents the scope of bot commands, covering all group and supergroup chats.

#### BotCommandScopeAllChatAdministrators

Represents the scope of bot commands, covering all group and supergroup chat administrators.

#### BotCommandScopeChat

Represents the scope of bot commands, covering a specific chat.

#### BotCommandScopeChatAdministrators

Represents the scope of bot commands, covering all administrators of a specific group or supergroup chat.

#### BotCommandScopeChatMember

Represents the scope of bot commands, covering a specific member of a group or supergroup chat.

#### BotName

This object represents the bot's name.

#### BotDescription

This object represents the bot's description.

#### BotShortDescription

This object represents the bot's short description.

#### MenuButton

This object describes the bot's menu button in a private chat. It should be one of

- MenuButtonCommands

- MenuButtonWebApp

- MenuButtonDefault

If a menu button other than MenuButtonDefault is set for a private chat, then it is applied in the chat. Otherwise the default menu button is applied. By default, the menu button opens the list of bot commands.

#### MenuButtonCommands

Represents a menu button, which opens the bot's list of commands.

#### MenuButtonWebApp

Represents a menu button, which launches a Web App.

#### MenuButtonDefault

Describes that no specific value for the menu button was set.

#### ChatBoostSource

This object describes the source of a chat boost. It can be one of

- ChatBoostSourcePremium

- ChatBoostSourceGiftCode

- ChatBoostSourceGiveaway

#### ChatBoostSourcePremium

The boost was obtained by subscribing to Telegram Premium or by gifting a Telegram Premium subscription to another user.

#### ChatBoostSourceGiftCode

The boost was obtained by the creation of Telegram Premium gift codes to boost a chat. Each such code boosts the chat 4 times for the duration of the corresponding Telegram Premium subscription.

#### ChatBoostSourceGiveaway

The boost was obtained by the creation of a Telegram Premium or a Telegram Star giveaway. This boosts the chat 4 times for the duration of the corresponding Telegram Premium subscription for Telegram Premium giveaways and prize_star_count / 500 times for one year for Telegram Star giveaways.

#### ChatBoost

This object contains information about a chat boost.

#### ChatBoostUpdated

This object represents a boost added to a chat or changed.

#### ChatBoostRemoved

This object represents a boost removed from a chat.

#### UserChatBoosts

This object represents a list of boosts added to a chat by a user.

#### BusinessBotRights

Represents the rights of a business bot.

#### BusinessConnection

Describes the connection of the bot with a business account.

#### BusinessMessagesDeleted

This object is received when messages are deleted from a connected business account.

#### ResponseParameters

Describes why a request was unsuccessful.

#### InputMedia

This object represents the content of a media message to be sent. It should be one of

- InputMediaAnimation

- InputMediaDocument

- InputMediaAudio

- InputMediaPhoto

- InputMediaVideo

#### InputMediaPhoto

Represents a photo to be sent.

#### InputMediaVideo

Represents a video to be sent.

#### InputMediaAnimation

Represents an animation file (GIF or H.264/MPEG-4 AVC video without sound) to be sent.

#### InputMediaAudio

Represents an audio file to be treated as music to be sent.

#### InputMediaDocument

Represents a general file to be sent.

#### InputFile

This object represents the contents of a file to be uploaded. Must be posted using multipart/form-data in the usual way that files are uploaded via the browser.

#### InputPaidMedia

This object describes the paid media to be sent. Currently, it can be one of

- InputPaidMediaPhoto

- InputPaidMediaVideo

#### InputPaidMediaPhoto

The paid media to send is a photo.

#### InputPaidMediaVideo

The paid media to send is a video.

#### InputProfilePhoto

This object describes a profile photo to set. Currently, it can be one of

- InputProfilePhotoStatic

- InputProfilePhotoAnimated

#### InputProfilePhotoStatic

A static profile photo in the .JPG format.

#### InputProfilePhotoAnimated

An animated profile photo in the MPEG4 format.

#### InputStoryContent

This object describes the content of a story to post. Currently, it can be one of

- InputStoryContentPhoto

- InputStoryContentVideo

#### InputStoryContentPhoto

Describes a photo to post as a story.

#### InputStoryContentVideo

Describes a video to post as a story.

#### Sending files

There are three ways to send files (photos, stickers, audio, media, etc.):

Sending by file_id

- It is not possible to change the file type when resending by file_id. I.e. a video can't be sent as a photo, a photo can't be sent as a document, etc.

- It is not possible to resend thumbnails.

- Resending a photo by file_id will send all of its sizes.

- file_id is unique for each individual bot and can't be transferred from one bot to another.

- file_id uniquely identifies a file, but a file can have different valid file_ids even for the same bot.

Sending by URL

- When sending by URL the target file must have the correct MIME type (e.g., audio/mpeg for sendAudio, etc.).

- In sendDocument, sending by URL will currently only work for .PDF and .ZIP files.

- To use sendVoice, the file must have the type audio/ogg and be no more than 1MB in size. 1-20MB voice notes will be sent as files.

- Other configurations may work but we can't guarantee that they will.

#### Accent colors

Colors with identifiers 0 (red), 1 (orange), 2 (purple/violet), 3 (green), 4 (cyan), 5 (blue), 6 (pink) can be customized by app themes. Additionally, the following colors in RGB format are currently in use.





#### Profile accent colors

Currently, the following colors in RGB format are in use for profile backgrounds.





#### Inline mode objects

Objects and methods used in the inline mode are described in the Inline mode section.

### Available methods

> All methods in the Bot API are case-insensitive. We support GET and POST HTTP methods. Use either URL query string or application/json or application/x-www-form-urlencoded or multipart/form-data for passing parameters in Bot API requests.On successful call, a JSON-object containing the result will be returned.

#### getMe

A simple method for testing your bot's authentication token. Requires no parameters. Returns basic information about the bot in form of a User object.

#### logOut

Use this method to log out from the cloud Bot API server before launching the bot locally. You must log out the bot before running it locally, otherwise there is no guarantee that the bot will receive updates. After a successful call, you can immediately log in on a local server, but will not be able to log in back to the cloud Bot API server for 10 minutes. Returns True on success. Requires no parameters.

#### close

Use this method to close the bot instance before moving it from one local server to another. You need to delete the webhook before calling this method to ensure that the bot isn't launched again after server restart. The method will return error 429 in the first 10 minutes after the bot is launched. Returns True on success. Requires no parameters.

#### sendMessage

Use this method to send text messages. On success, the sent Message is returned.

#### Formatting options

The Bot API supports basic formatting for messages. You can use bold, italic, underlined, strikethrough, spoiler text, block quotations as well as inline links and pre-formatted code in your bots' messages. Telegram clients will render them accordingly. You can specify text entities directly, or use markdown-style or HTML-style formatting.

Note that Telegram clients will display an alert to the user before opening an inline link ('Open this link?' together with the full URL).

Message entities can be nested, providing following restrictions are met:- If two entities have common characters, then one of them is fully contained inside another.- bold, italic, underline, strikethrough, and spoiler entities can contain and can be part of any other entities, except pre and code.- blockquote and expandable_blockquote entities can't be nested.- All other entities can't contain each other.

Links tg://user?id=<user_id> can be used to mention a user by their identifier without using a username. Please note:

- These links will work only if they are used inside an inline link or in an inline keyboard button. For example, they will not work, when used in a message text.

- Unless the user is a member of the chat where they were mentioned, these mentions are only guaranteed to work if the user has contacted the bot in private in the past or has sent a callback query to the bot via an inline button and doesn't have Forwarded Messages privacy enabled for the bot.

You can find the list of programming and markup languages for which syntax highlighting is supported at libprisma#supported-languages.

###### MarkdownV2 style

To use this mode, pass MarkdownV2 in the parse_mode field. Use the following syntax in your message:

```
*bold \*text*
_italic \*text_
__underline__
~strikethrough~
||spoiler||
*bold _italic bold ~italic bold strikethrough ||italic bold strikethrough spoiler||~ __underline italic bold___ bold*
[inline URL](http://www.example.com/)
[inline mention of a user](tg://user?id=123456789)
![](tg://emoji?id=5368324170671202286)
`inline fixed-width code`
```
pre-formatted fixed-width code block
```
```python
pre-formatted fixed-width code block written in the Python programming language
```
>Block quotation started
>Block quotation continued
>Block quotation continued
>Block quotation continued
>The last line of the block quotation
**>The expandable block quotation started right after the previous block quotation
>It is separated from the previous block quotation by an empty bold entity
>Expandable block quotation continued
>Hidden by default part of the expandable block quotation started
>Expandable block quotation continued
>The last line of the expandable block quotation with the expandability mark||
```

Please note:

- Any character with code between 1 and 126 inclusively can be escaped anywhere with a preceding '\' character, in which case it is treated as an ordinary character and not a part of the markup. This implies that '\' character usually must be escaped with a preceding '\' character.

- Inside pre and code entities, all '`' and '\' characters must be escaped with a preceding '\' character.

- Inside the (...) part of the inline link and custom emoji definition, all ')' and '\' must be escaped with a preceding '\' character.

- In all other places characters '_', '*', '[', ']', '(', ')', '~', '`', '>', '#', '+', '-', '=', '|', '{', '}', '.', '!' must be escaped with the preceding character '\'.

- In case of ambiguity between italic and underline entities __ is always greedily treated from left to right as beginning or end of an underline entity, so instead of ___italic underline___ use ___italic underline_**__, adding an empty bold entity as a separator.

- A valid emoji must be provided as an alternative value for the custom emoji. The emoji will be shown instead of the custom emoji in places where a custom emoji cannot be displayed (e.g., system notifications) or if the message is forwarded by a non-premium user. It is recommended to use the emoji from the emoji field of the custom emoji sticker.

- Custom emoji entities can only be used by bots that purchased additional usernames on Fragment.

###### HTML style

To use this mode, pass HTML in the parse_mode field. The following tags are currently supported:

```
<b>bold</b>, <strong>bold</strong>
<i>italic</i>, <em>italic</em>
<u>underline</u>, <ins>underline</ins>
<s>strikethrough</s>, <strike>strikethrough</strike>, <del>strikethrough</del>
<span class="tg-spoiler">spoiler</span>, <tg-spoiler>spoiler</tg-spoiler>
<b>bold <i>italic bold <s>italic bold strikethrough <span class="tg-spoiler">italic bold strikethrough spoiler</span></s> <u>underline italic bold</u></i> bold</b>
<a href="http://www.example.com/">inline URL</a>
<a href="tg://user?id=123456789">inline mention of a user</a>
<tg-emoji emoji-id="5368324170671202286"></tg-emoji>
<code>inline fixed-width code</code>
<pre>pre-formatted fixed-width code block</pre>
<pre><code class="language-python">pre-formatted fixed-width code block written in the Python programming language</code></pre>
<blockquote>Block quotation started\nBlock quotation continued\nThe last line of the block quotation</blockquote>
<blockquote expandable>Expandable block quotation started\nExpandable block quotation continued\nExpandable block quotation continued\nHidden by default part of the block quotation started\nExpandable block quotation continued\nThe last line of the block quotation</blockquote>
```

Please note:

- Only the tags mentioned above are currently supported.

- All <, > and & symbols that are not a part of a tag or an HTML entity must be replaced with the corresponding HTML entities (< with &lt;, > with &gt; and & with &amp;).

- All numerical HTML entities are supported.

- The API currently supports only the following named HTML entities: &lt;, &gt;, &amp; and &quot;.

- Use nested pre and code tags, to define programming language for pre entity.

- Programming language can't be specified for standalone code tags.

- A valid emoji must be used as the content of the tg-emoji tag. The emoji will be shown instead of the custom emoji in places where a custom emoji cannot be displayed (e.g., system notifications) or if the message is forwarded by a non-premium user. It is recommended to use the emoji from the emoji field of the custom emoji sticker.

- Custom emoji entities can only be used by bots that purchased additional usernames on Fragment.

###### Markdown style

This is a legacy mode, retained for backward compatibility. To use this mode, pass Markdown in the parse_mode field. Use the following syntax in your message:

```
*bold text*
_italic text_
[inline URL](http://www.example.com/)
[inline mention of a user](tg://user?id=123456789)
`inline fixed-width code`
```
pre-formatted fixed-width code block
```
```python
pre-formatted fixed-width code block written in the Python programming language
```
```

Please note:

- Entities must not be nested, use parse mode MarkdownV2 instead.

- There is no way to specify “underline”, “strikethrough”, “spoiler”, “blockquote”, “expandable_blockquote” and “custom_emoji” entities, use parse mode MarkdownV2 instead.

- To escape characters '_', '*', '`', '[' outside of an entity, prepend the character '\' before them.

- Escaping inside entities is not allowed, so entity must be closed first and reopened again: use _snake_\__case_ for italic snake_case and *2*\**2=4* for bold 2*2=4.

#### Paid Broadcasts

By default, all bots are able to broadcast up to 30 messages per second to their users. Developers can increase this limit by enabling Paid Broadcasts in @Botfather - allowing their bot to broadcast up to 1000 messages per second.

Each message broadcasted over the free amount of 30 messages per second incurs a cost of 0.1 Stars per message, paid with Telegram Stars from the bot's balance. In order to use this feature, a bot must have at least 10,000 Stars on its balance.

> Bots with increased limits are only charged for messages that are broadcasted successfully.

#### forwardMessage

Use this method to forward messages of any kind. Service messages and messages with protected content can't be forwarded. On success, the sent Message is returned.

#### forwardMessages

Use this method to forward multiple messages of any kind. If some of the specified messages can't be found or forwarded, they are skipped. Service messages and messages with protected content can't be forwarded. Album grouping is kept for forwarded messages. On success, an array of MessageId of the sent messages is returned.

#### copyMessage

Use this method to copy messages of any kind. Service messages, paid media messages, giveaway messages, giveaway winners messages, and invoice messages can't be copied. A quiz poll can be copied only if the value of the field correct_option_id is known to the bot. The method is analogous to the method forwardMessage, but the copied message doesn't have a link to the original message. Returns the MessageId of the sent message on success.

#### copyMessages

Use this method to copy messages of any kind. If some of the specified messages can't be found or copied, they are skipped. Service messages, paid media messages, giveaway messages, giveaway winners messages, and invoice messages can't be copied. A quiz poll can be copied only if the value of the field correct_option_id is known to the bot. The method is analogous to the method forwardMessages, but the copied messages don't have a link to the original message. Album grouping is kept for copied messages. On success, an array of MessageId of the sent messages is returned.

#### sendPhoto

Use this method to send photos. On success, the sent Message is returned.

#### sendAudio

Use this method to send audio files, if you want Telegram clients to display them in the music player. Your audio must be in the .MP3 or .M4A format. On success, the sent Message is returned. Bots can currently send audio files of up to 50 MB in size, this limit may be changed in the future.

For sending voice messages, use the sendVoice method instead.

#### sendDocument

Use this method to send general files. On success, the sent Message is returned. Bots can currently send files of any type of up to 50 MB in size, this limit may be changed in the future.

#### sendVideo

Use this method to send video files, Telegram clients support MPEG4 videos (other formats may be sent as Document). On success, the sent Message is returned. Bots can currently send video files of up to 50 MB in size, this limit may be changed in the future.

#### sendAnimation

Use this method to send animation files (GIF or H.264/MPEG-4 AVC video without sound). On success, the sent Message is returned. Bots can currently send animation files of up to 50 MB in size, this limit may be changed in the future.

#### sendVoice

Use this method to send audio files, if you want Telegram clients to display the file as a playable voice message. For this to work, your audio must be in an .OGG file encoded with OPUS, or in .MP3 format, or in .M4A format (other formats may be sent as Audio or Document). On success, the sent Message is returned. Bots can currently send voice messages of up to 50 MB in size, this limit may be changed in the future.

#### sendVideoNote

As of v.4.0, Telegram clients support rounded square MPEG4 videos of up to 1 minute long. Use this method to send video messages. On success, the sent Message is returned.

#### sendPaidMedia

Use this method to send paid media. On success, the sent Message is returned.

#### sendMediaGroup

Use this method to send a group of photos, videos, documents or audios as an album. Documents and audio files can be only grouped in an album with messages of the same type. On success, an array of Message objects that were sent is returned.

#### sendLocation

Use this method to send point on the map. On success, the sent Message is returned.

#### sendVenue

Use this method to send information about a venue. On success, the sent Message is returned.

#### sendContact

Use this method to send phone contacts. On success, the sent Message is returned.

#### sendPoll

Use this method to send a native poll. On success, the sent Message is returned.

#### sendChecklist

Use this method to send a checklist on behalf of a connected business account. On success, the sent Message is returned.

#### sendDice

Use this method to send an animated emoji that will display a random value. On success, the sent Message is returned.

#### sendMessageDraft

Use this method to stream a partial message to a user while the message is being generated; supported only for bots with forum topic mode enabled. Returns True on success.

#### sendChatAction

Use this method when you need to tell the user that something is happening on the bot's side. The status is set for 5 seconds or less (when a message arrives from your bot, Telegram clients clear its typing status). Returns True on success.

> Example: The ImageBot needs some time to process a request and upload the image. Instead of sending a text message along the lines of “Retrieving image, please wait…”, the bot may use sendChatAction with action = upload_photo. The user will see a “sending photo” status for the bot.

We only recommend using this method when a response from the bot will take a noticeable amount of time to arrive.

#### setMessageReaction

Use this method to change the chosen reactions on a message. Service messages of some types can't be reacted to. Automatically forwarded messages from a channel to its discussion group have the same available reactions as messages in the channel. Bots can't use paid reactions. Returns True on success.

#### getUserProfilePhotos

Use this method to get a list of profile pictures for a user. Returns a UserProfilePhotos object.

#### setUserEmojiStatus

Changes the emoji status for a given user that previously allowed the bot to manage their emoji status via the Mini App method requestEmojiStatusAccess. Returns True on success.

#### getFile

Use this method to get basic information about a file and prepare it for downloading. For the moment, bots can download files of up to 20MB in size. On success, a File object is returned. The file can then be downloaded via the link https://api.telegram.org/file/bot<token>/<file_path>, where <file_path> is taken from the response. It is guaranteed that the link will be valid for at least 1 hour. When the link expires, a new one can be requested by calling getFile again.

Note: This function may not preserve the original file name and MIME type. You should save the file's MIME type and name (if available) when the File object is received.

#### banChatMember

Use this method to ban a user in a group, a supergroup or a channel. In the case of supergroups and channels, the user will not be able to return to the chat on their own using invite links, etc., unless unbanned first. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns True on success.

#### unbanChatMember

Use this method to unban a previously banned user in a supergroup or channel. The user will not return to the group or channel automatically, but will be able to join via link, etc. The bot must be an administrator for this to work. By default, this method guarantees that after the call the user is not a member of the chat, but will be able to join it. So if the user is a member of the chat they will also be removed from the chat. If you don't want this, use the parameter only_if_banned. Returns True on success.

#### restrictChatMember

Use this method to restrict a user in a supergroup. The bot must be an administrator in the supergroup for this to work and must have the appropriate administrator rights. Pass True for all permissions to lift restrictions from a user. Returns True on success.

#### promoteChatMember

Use this method to promote or demote a user in a supergroup or a channel. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Pass False for all boolean parameters to demote a user. Returns True on success.

#### setChatAdministratorCustomTitle

Use this method to set a custom title for an administrator in a supergroup promoted by the bot. Returns True on success.

#### banChatSenderChat

Use this method to ban a channel chat in a supergroup or a channel. Until the chat is unbanned, the owner of the banned chat won't be able to send messages on behalf of any of their channels. The bot must be an administrator in the supergroup or channel for this to work and must have the appropriate administrator rights. Returns True on success.

#### unbanChatSenderChat

Use this method to unban a previously banned channel chat in a supergroup or channel. The bot must be an administrator for this to work and must have the appropriate administrator rights. Returns True on success.

#### setChatPermissions

Use this method to set default chat permissions for all members. The bot must be an administrator in the group or a supergroup for this to work and must have the can_restrict_members administrator rights. Returns True on success.

#### exportChatInviteLink

Use this method to generate a new primary invite link for a chat; any previously generated primary link is revoked. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the new invite link as String on success.

> Note: Each administrator in a chat generates their own invite links. Bots can't use invite links generated by other administrators. If you want your bot to work with invite links, it will need to generate its own link using exportChatInviteLink or by calling the getChat method. If your bot needs to generate a new primary invite link replacing its previous one, use exportChatInviteLink again.

#### createChatInviteLink

Use this method to create an additional invite link for a chat. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. The link can be revoked using the method revokeChatInviteLink. Returns the new invite link as ChatInviteLink object.

#### editChatInviteLink

Use this method to edit a non-primary invite link created by the bot. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the edited invite link as a ChatInviteLink object.

#### createChatSubscriptionInviteLink

Use this method to create a subscription invite link for a channel chat. The bot must have the can_invite_users administrator rights. The link can be edited using the method editChatSubscriptionInviteLink or revoked using the method revokeChatInviteLink. Returns the new invite link as a ChatInviteLink object.

#### editChatSubscriptionInviteLink

Use this method to edit a subscription invite link created by the bot. The bot must have the can_invite_users administrator rights. Returns the edited invite link as a ChatInviteLink object.

#### revokeChatInviteLink

Use this method to revoke an invite link created by the bot. If the primary link is revoked, a new link is automatically generated. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the revoked invite link as ChatInviteLink object.

#### approveChatJoinRequest

Use this method to approve a chat join request. The bot must be an administrator in the chat for this to work and must have the can_invite_users administrator right. Returns True on success.

#### declineChatJoinRequest

Use this method to decline a chat join request. The bot must be an administrator in the chat for this to work and must have the can_invite_users administrator right. Returns True on success.

#### setChatPhoto

Use this method to set a new profile photo for the chat. Photos can't be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns True on success.

#### deleteChatPhoto

Use this method to delete a chat photo. Photos can't be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns True on success.

#### setChatTitle

Use this method to change the title of a chat. Titles can't be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns True on success.

#### setChatDescription

Use this method to change the description of a group, a supergroup or a channel. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns True on success.

#### pinChatMessage

Use this method to add a message to the list of pinned messages in a chat. In private chats and channel direct messages chats, all non-service messages can be pinned. Conversely, the bot must be an administrator with the 'can_pin_messages' right or the 'can_edit_messages' right to pin messages in groups and channels respectively. Returns True on success.

#### unpinChatMessage

Use this method to remove a message from the list of pinned messages in a chat. In private chats and channel direct messages chats, all messages can be unpinned. Conversely, the bot must be an administrator with the 'can_pin_messages' right or the 'can_edit_messages' right to unpin messages in groups and channels respectively. Returns True on success.

#### unpinAllChatMessages

Use this method to clear the list of pinned messages in a chat. In private chats and channel direct messages chats, no additional rights are required to unpin all pinned messages. Conversely, the bot must be an administrator with the 'can_pin_messages' right or the 'can_edit_messages' right to unpin all pinned messages in groups and channels respectively. Returns True on success.

#### leaveChat

Use this method for your bot to leave a group, supergroup or channel. Returns True on success.

#### getChat

Use this method to get up-to-date information about the chat. Returns a ChatFullInfo object on success.

#### getChatAdministrators

Use this method to get a list of administrators in a chat, which aren't bots. Returns an Array of ChatMember objects.

#### getChatMemberCount

Use this method to get the number of members in a chat. Returns Int on success.

#### getChatMember

Use this method to get information about a member of a chat. The method is only guaranteed to work for other users if the bot is an administrator in the chat. Returns a ChatMember object on success.

#### setChatStickerSet

Use this method to set a new group sticker set for a supergroup. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Use the field can_set_sticker_set optionally returned in getChat requests to check if the bot can use this method. Returns True on success.

#### deleteChatStickerSet

Use this method to delete a group sticker set from a supergroup. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Use the field can_set_sticker_set optionally returned in getChat requests to check if the bot can use this method. Returns True on success.

#### getForumTopicIconStickers

Use this method to get custom emoji stickers, which can be used as a forum topic icon by any user. Requires no parameters. Returns an Array of Sticker objects.

#### createForumTopic

Use this method to create a topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights. Returns information about the created topic as a ForumTopic object.

#### editForumTopic

Use this method to edit name and icon of a topic in a forum supergroup chat or a private chat with a user. In the case of a supergroup chat the bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights, unless it is the creator of the topic. Returns True on success.

#### closeForumTopic

Use this method to close an open topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights, unless it is the creator of the topic. Returns True on success.

#### reopenForumTopic

Use this method to reopen a closed topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights, unless it is the creator of the topic. Returns True on success.

#### deleteForumTopic

Use this method to delete a forum topic along with all its messages in a forum supergroup chat or a private chat with a user. In the case of a supergroup chat the bot must be an administrator in the chat for this to work and must have the can_delete_messages administrator rights. Returns True on success.

#### unpinAllForumTopicMessages

Use this method to clear the list of pinned messages in a forum topic in a forum supergroup chat or a private chat with a user. In the case of a supergroup chat the bot must be an administrator in the chat for this to work and must have the can_pin_messages administrator right in the supergroup. Returns True on success.

#### editGeneralForumTopic

Use this method to edit the name of the 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights. Returns True on success.

#### closeGeneralForumTopic

Use this method to close an open 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights. Returns True on success.

#### reopenGeneralForumTopic

Use this method to reopen a closed 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights. The topic will be automatically unhidden if it was hidden. Returns True on success.

#### hideGeneralForumTopic

Use this method to hide the 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights. The topic will be automatically closed if it was open. Returns True on success.

#### unhideGeneralForumTopic

Use this method to unhide the 'General' topic in a forum supergroup chat. The bot must be an administrator in the chat for this to work and must have the can_manage_topics administrator rights. Returns True on success.

#### unpinAllGeneralForumTopicMessages

Use this method to clear the list of pinned messages in a General forum topic. The bot must be an administrator in the chat for this to work and must have the can_pin_messages administrator right in the supergroup. Returns True on success.

#### answerCallbackQuery

Use this method to send answers to callback queries sent from inline keyboards. The answer will be displayed to the user as a notification at the top of the chat screen or as an alert. On success, True is returned.

> Alternatively, the user can be redirected to the specified Game URL. For this option to work, you must first create a game for your bot via @BotFather and accept the terms. Otherwise, you may use links like t.me/your_bot?start=XXXX that open your bot with a parameter.

#### getUserChatBoosts

Use this method to get the list of boosts added to a chat by a user. Requires administrator rights in the chat. Returns a UserChatBoosts object.

#### getBusinessConnection

Use this method to get information about the connection of the bot with a business account. Returns a BusinessConnection object on success.

#### setMyCommands

Use this method to change the list of the bot's commands. See this manual for more details about bot commands. Returns True on success.

#### deleteMyCommands

Use this method to delete the list of the bot's commands for the given scope and user language. After deletion, higher level commands will be shown to affected users. Returns True on success.

#### getMyCommands

Use this method to get the current list of the bot's commands for the given scope and user language. Returns an Array of BotCommand objects. If commands aren't set, an empty list is returned.

#### setMyName

Use this method to change the bot's name. Returns True on success.

#### getMyName

Use this method to get the current bot name for the given user language. Returns BotName on success.

#### setMyDescription

Use this method to change the bot's description, which is shown in the chat with the bot if the chat is empty. Returns True on success.

#### getMyDescription

Use this method to get the current bot description for the given user language. Returns BotDescription on success.

#### setMyShortDescription

Use this method to change the bot's short description, which is shown on the bot's profile page and is sent together with the link when users share the bot. Returns True on success.

#### getMyShortDescription

Use this method to get the current bot short description for the given user language. Returns BotShortDescription on success.

#### setChatMenuButton

Use this method to change the bot's menu button in a private chat, or the default menu button. Returns True on success.

#### getChatMenuButton

Use this method to get the current value of the bot's menu button in a private chat, or the default menu button. Returns MenuButton on success.

#### setMyDefaultAdministratorRights

Use this method to change the default administrator rights requested by the bot when it's added as an administrator to groups or channels. These rights will be suggested to users, but they are free to modify the list before adding the bot. Returns True on success.

#### getMyDefaultAdministratorRights

Use this method to get the current default administrator rights of the bot. Returns ChatAdministratorRights on success.

#### getAvailableGifts

Returns the list of gifts that can be sent by the bot to users and channel chats. Requires no parameters. Returns a Gifts object.

#### sendGift

Sends a gift to the given user or channel chat. The gift can't be converted to Telegram Stars by the receiver. Returns True on success.

#### giftPremiumSubscription

Gifts a Telegram Premium subscription to the given user. Returns True on success.

#### verifyUser

Verifies a user on behalf of the organization which is represented by the bot. Returns True on success.

#### verifyChat

Verifies a chat on behalf of the organization which is represented by the bot. Returns True on success.

#### removeUserVerification

Removes verification from a user who is currently verified on behalf of the organization represented by the bot. Returns True on success.

#### removeChatVerification

Removes verification from a chat that is currently verified on behalf of the organization represented by the bot. Returns True on success.

#### readBusinessMessage

Marks incoming message as read on behalf of a business account. Requires the can_read_messages business bot right. Returns True on success.

#### deleteBusinessMessages

Delete messages on behalf of a business account. Requires the can_delete_sent_messages business bot right to delete messages sent by the bot itself, or the can_delete_all_messages business bot right to delete any message. Returns True on success.

#### setBusinessAccountName

Changes the first and last name of a managed business account. Requires the can_change_name business bot right. Returns True on success.

#### setBusinessAccountUsername

Changes the username of a managed business account. Requires the can_change_username business bot right. Returns True on success.

#### setBusinessAccountBio

Changes the bio of a managed business account. Requires the can_change_bio business bot right. Returns True on success.

#### setBusinessAccountProfilePhoto

Changes the profile photo of a managed business account. Requires the can_edit_profile_photo business bot right. Returns True on success.

#### removeBusinessAccountProfilePhoto

Removes the current profile photo of a managed business account. Requires the can_edit_profile_photo business bot right. Returns True on success.

#### setBusinessAccountGiftSettings

Changes the privacy settings pertaining to incoming gifts in a managed business account. Requires the can_change_gift_settings business bot right. Returns True on success.

#### getBusinessAccountStarBalance

Returns the amount of Telegram Stars owned by a managed business account. Requires the can_view_gifts_and_stars business bot right. Returns StarAmount on success.

#### transferBusinessAccountStars

Transfers Telegram Stars from the business account balance to the bot's balance. Requires the can_transfer_stars business bot right. Returns True on success.

#### getBusinessAccountGifts

Returns the gifts received and owned by a managed business account. Requires the can_view_gifts_and_stars business bot right. Returns OwnedGifts on success.

#### getUserGifts

Returns the gifts owned and hosted by a user. Returns OwnedGifts on success.

#### getChatGifts

Returns the gifts owned by a chat. Returns OwnedGifts on success.

#### convertGiftToStars

Converts a given regular gift to Telegram Stars. Requires the can_convert_gifts_to_stars business bot right. Returns True on success.

#### upgradeGift

Upgrades a given regular gift to a unique gift. Requires the can_transfer_and_upgrade_gifts business bot right. Additionally requires the can_transfer_stars business bot right if the upgrade is paid. Returns True on success.

#### transferGift

Transfers an owned unique gift to another user. Requires the can_transfer_and_upgrade_gifts business bot right. Requires can_transfer_stars business bot right if the transfer is paid. Returns True on success.

#### postStory

Posts a story on behalf of a managed business account. Requires the can_manage_stories business bot right. Returns Story on success.

#### repostStory

Reposts a story on behalf of a business account from another business account. Both business accounts must be managed by the same bot, and the story on the source account must have been posted (or reposted) by the bot. Requires the can_manage_stories business bot right for both business accounts. Returns Story on success.

#### editStory

Edits a story previously posted by the bot on behalf of a managed business account. Requires the can_manage_stories business bot right. Returns Story on success.

#### deleteStory

Deletes a story previously posted by the bot on behalf of a managed business account. Requires the can_manage_stories business bot right. Returns True on success.

#### Inline mode methods

Methods and objects used in the inline mode are described in the Inline mode section.

### Updating messages

The following methods allow you to change an existing message in the message history instead of sending a new one with a result of an action. This is most useful for messages with inline keyboards using callback queries, but can also help reduce clutter in conversations with regular chat bots.

Please note, that it is currently only possible to edit messages without reply_markup or with inline keyboards.

#### editMessageText

Use this method to edit text and game messages. On success, if the edited message is not an inline message, the edited Message is returned, otherwise True is returned. Note that business messages that were not sent by the bot and do not contain an inline keyboard can only be edited within 48 hours from the time they were sent.

#### editMessageCaption

Use this method to edit captions of messages. On success, if the edited message is not an inline message, the edited Message is returned, otherwise True is returned. Note that business messages that were not sent by the bot and do not contain an inline keyboard can only be edited within 48 hours from the time they were sent.

#### editMessageMedia

Use this method to edit animation, audio, document, photo, or video messages, or to add media to text messages. If a message is part of a message album, then it can be edited only to an audio for audio albums, only to a document for document albums and to a photo or a video otherwise. When an inline message is edited, a new file can't be uploaded; use a previously uploaded file via its file_id or specify a URL. On success, if the edited message is not an inline message, the edited Message is returned, otherwise True is returned. Note that business messages that were not sent by the bot and do not contain an inline keyboard can only be edited within 48 hours from the time they were sent.

#### editMessageLiveLocation

Use this method to edit live location messages. A location can be edited until its live_period expires or editing is explicitly disabled by a call to stopMessageLiveLocation. On success, if the edited message is not an inline message, the edited Message is returned, otherwise True is returned.

#### stopMessageLiveLocation

Use this method to stop updating a live location message before live_period expires. On success, if the message is not an inline message, the edited Message is returned, otherwise True is returned.

#### editMessageChecklist

Use this method to edit a checklist on behalf of a connected business account. On success, the edited Message is returned.

#### editMessageReplyMarkup

Use this method to edit only the reply markup of messages. On success, if the edited message is not an inline message, the edited Message is returned, otherwise True is returned. Note that business messages that were not sent by the bot and do not contain an inline keyboard can only be edited within 48 hours from the time they were sent.

#### stopPoll

Use this method to stop a poll which was sent by the bot. On success, the stopped Poll is returned.

#### approveSuggestedPost

Use this method to approve a suggested post in a direct messages chat. The bot must have the 'can_post_messages' administrator right in the corresponding channel chat. Returns True on success.

#### declineSuggestedPost

Use this method to decline a suggested post in a direct messages chat. The bot must have the 'can_manage_direct_messages' administrator right in the corresponding channel chat. Returns True on success.

#### deleteMessage

Use this method to delete a message, including service messages, with the following limitations:- A message can only be deleted if it was sent less than 48 hours ago.- Service messages about a supergroup, channel, or forum topic creation can't be deleted.- A dice message in a private chat can only be deleted if it was sent more than 24 hours ago.- Bots can delete outgoing messages in private chats, groups, and supergroups.- Bots can delete incoming messages in private chats.- Bots granted can_post_messages permissions can delete outgoing messages in channels.- If the bot is an administrator of a group, it can delete any message there.- If the bot has can_delete_messages administrator right in a supergroup or a channel, it can delete any message there.- If the bot has can_manage_direct_messages administrator right in a channel, it can delete any message in the corresponding direct messages chat.Returns True on success.

#### deleteMessages

Use this method to delete multiple messages simultaneously. If some of the specified messages can't be found, they are skipped. Returns True on success.

### Stickers

The following methods and objects allow your bot to handle stickers and sticker sets.

#### Sticker

This object represents a sticker.

#### StickerSet

This object represents a sticker set.

#### MaskPosition

This object describes the position on faces where a mask should be placed by default.

#### InputSticker

This object describes a sticker to be added to a sticker set.

#### sendSticker

Use this method to send static .WEBP, animated .TGS, or video .WEBM stickers. On success, the sent Message is returned.

#### getStickerSet

Use this method to get a sticker set. On success, a StickerSet object is returned.

#### getCustomEmojiStickers

Use this method to get information about custom emoji stickers by their identifiers. Returns an Array of Sticker objects.

#### uploadStickerFile

Use this method to upload a file with a sticker for later use in the createNewStickerSet, addStickerToSet, or replaceStickerInSet methods (the file can be used multiple times). Returns the uploaded File on success.

#### createNewStickerSet

Use this method to create a new sticker set owned by a user. The bot will be able to edit the sticker set thus created. Returns True on success.

#### addStickerToSet

Use this method to add a new sticker to a set created by the bot. Emoji sticker sets can have up to 200 stickers. Other sticker sets can have up to 120 stickers. Returns True on success.

#### setStickerPositionInSet

Use this method to move a sticker in a set created by the bot to a specific position. Returns True on success.

#### deleteStickerFromSet

Use this method to delete a sticker from a set created by the bot. Returns True on success.

#### replaceStickerInSet

Use this method to replace an existing sticker in a sticker set with a new one. The method is equivalent to calling deleteStickerFromSet, then addStickerToSet, then setStickerPositionInSet. Returns True on success.

#### setStickerEmojiList

Use this method to change the list of emoji assigned to a regular or custom emoji sticker. The sticker must belong to a sticker set created by the bot. Returns True on success.

#### setStickerKeywords

Use this method to change search keywords assigned to a regular or custom emoji sticker. The sticker must belong to a sticker set created by the bot. Returns True on success.

#### setStickerMaskPosition

Use this method to change the mask position of a mask sticker. The sticker must belong to a sticker set that was created by the bot. Returns True on success.

#### setStickerSetTitle

Use this method to set the title of a created sticker set. Returns True on success.

#### setStickerSetThumbnail

Use this method to set the thumbnail of a regular or mask sticker set. The format of the thumbnail file must match the format of the stickers in the set. Returns True on success.

#### setCustomEmojiStickerSetThumbnail

Use this method to set the thumbnail of a custom emoji sticker set. Returns True on success.

#### deleteStickerSet

Use this method to delete a sticker set that was created by the bot. Returns True on success.

### Inline mode

The following methods and objects allow your bot to work in inline mode.Please see our Introduction to Inline bots for more details.

To enable this option, send the /setinline command to @BotFather and provide the placeholder text that the user will see in the input field after typing your bot's name.

#### InlineQuery

This object represents an incoming inline query. When the user sends an empty query, your bot could return some default or trending results.

#### answerInlineQuery

Use this method to send answers to an inline query. On success, True is returned.No more than 50 results per query are allowed.

#### InlineQueryResultsButton

This object represents a button to be shown above inline query results. You must use exactly one of the optional fields.

#### InlineQueryResult

This object represents one result of an inline query. Telegram clients currently support results of the following 20 types:

- InlineQueryResultCachedAudio

- InlineQueryResultCachedDocument

- InlineQueryResultCachedGif

- InlineQueryResultCachedMpeg4Gif

- InlineQueryResultCachedPhoto

- InlineQueryResultCachedSticker

- InlineQueryResultCachedVideo

- InlineQueryResultCachedVoice

- InlineQueryResultArticle

- InlineQueryResultAudio

- InlineQueryResultContact

- InlineQueryResultGame

- InlineQueryResultDocument

- InlineQueryResultGif

- InlineQueryResultLocation

- InlineQueryResultMpeg4Gif

- InlineQueryResultPhoto

- InlineQueryResultVenue

- InlineQueryResultVideo

- InlineQueryResultVoice

Note: All URLs passed in inline query results will be available to end users and therefore must be assumed to be public.

#### InlineQueryResultArticle

Represents a link to an article or web page.

#### InlineQueryResultPhoto

Represents a link to a photo. By default, this photo will be sent by the user with optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the photo.

#### InlineQueryResultGif

Represents a link to an animated GIF file. By default, this animated GIF file will be sent by the user with optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the animation.

#### InlineQueryResultMpeg4Gif

Represents a link to a video animation (H.264/MPEG-4 AVC video without sound). By default, this animated MPEG-4 file will be sent by the user with optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the animation.

#### InlineQueryResultVideo

Represents a link to a page containing an embedded video player or a video file. By default, this video file will be sent by the user with an optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the video.

> If an InlineQueryResultVideo message contains an embedded video (e.g., YouTube), you must replace its content using input_message_content.

#### InlineQueryResultAudio

Represents a link to an MP3 audio file. By default, this audio file will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the audio.

#### InlineQueryResultVoice

Represents a link to a voice recording in an .OGG container encoded with OPUS. By default, this voice recording will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the the voice message.

#### InlineQueryResultDocument

Represents a link to a file. By default, this file will be sent by the user with an optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the file. Currently, only .PDF and .ZIP files can be sent using this method.

#### InlineQueryResultLocation

Represents a location on a map. By default, the location will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the location.

#### InlineQueryResultVenue

Represents a venue. By default, the venue will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the venue.

#### InlineQueryResultContact

Represents a contact with a phone number. By default, this contact will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the contact.

#### InlineQueryResultGame

Represents a Game.

#### InlineQueryResultCachedPhoto

Represents a link to a photo stored on the Telegram servers. By default, this photo will be sent by the user with an optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the photo.

#### InlineQueryResultCachedGif

Represents a link to an animated GIF file stored on the Telegram servers. By default, this animated GIF file will be sent by the user with an optional caption. Alternatively, you can use input_message_content to send a message with specified content instead of the animation.

#### InlineQueryResultCachedMpeg4Gif

Represents a link to a video animation (H.264/MPEG-4 AVC video without sound) stored on the Telegram servers. By default, this animated MPEG-4 file will be sent by the user with an optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the animation.

#### InlineQueryResultCachedSticker

Represents a link to a sticker stored on the Telegram servers. By default, this sticker will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the sticker.

#### InlineQueryResultCachedDocument

Represents a link to a file stored on the Telegram servers. By default, this file will be sent by the user with an optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the file.

#### InlineQueryResultCachedVideo

Represents a link to a video file stored on the Telegram servers. By default, this video file will be sent by the user with an optional caption. Alternatively, you can use input_message_content to send a message with the specified content instead of the video.

#### InlineQueryResultCachedVoice

Represents a link to a voice message stored on the Telegram servers. By default, this voice message will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the voice message.

#### InlineQueryResultCachedAudio

Represents a link to an MP3 audio file stored on the Telegram servers. By default, this audio file will be sent by the user. Alternatively, you can use input_message_content to send a message with the specified content instead of the audio.

#### InputMessageContent

This object represents the content of a message to be sent as a result of an inline query. Telegram clients currently support the following 5 types:

- InputTextMessageContent

- InputLocationMessageContent

- InputVenueMessageContent

- InputContactMessageContent

- InputInvoiceMessageContent

#### InputTextMessageContent

Represents the content of a text message to be sent as the result of an inline query.

#### InputLocationMessageContent

Represents the content of a location message to be sent as the result of an inline query.

#### InputVenueMessageContent

Represents the content of a venue message to be sent as the result of an inline query.

#### InputContactMessageContent

Represents the content of a contact message to be sent as the result of an inline query.

#### InputInvoiceMessageContent

Represents the content of an invoice message to be sent as the result of an inline query.

#### ChosenInlineResult

Represents a result of an inline query that was chosen by the user and sent to their chat partner.

Note: It is necessary to enable inline feedback via @BotFather in order to receive these objects in updates.

#### answerWebAppQuery

Use this method to set the result of an interaction with a Web App and send a corresponding message on behalf of the user to the chat from which the query originated. On success, a SentWebAppMessage object is returned.

#### SentWebAppMessage

Describes an inline message sent by a Web App on behalf of a user.

#### savePreparedInlineMessage

Stores a message that can be sent by a user of a Mini App. Returns a PreparedInlineMessage object.

#### PreparedInlineMessage

Describes an inline message to be sent by a user of a Mini App.

### Payments

Your bot can accept payments from Telegram users. Please see the introduction to payments for more details on the process and how to set up payments for your bot.

#### sendInvoice

Use this method to send invoices. On success, the sent Message is returned.

#### createInvoiceLink

Use this method to create a link for an invoice. Returns the created invoice link as String on success.

#### answerShippingQuery

If you sent an invoice requesting a shipping address and the parameter is_flexible was specified, the Bot API will send an Update with a shipping_query field to the bot. Use this method to reply to shipping queries. On success, True is returned.

#### answerPreCheckoutQuery

Once the user has confirmed their payment and shipping details, the Bot API sends the final confirmation in the form of an Update with the field pre_checkout_query. Use this method to respond to such pre-checkout queries. On success, True is returned. Note: The Bot API must receive an answer within 10 seconds after the pre-checkout query was sent.

#### getMyStarBalance

A method to get the current Telegram Stars balance of the bot. Requires no parameters. On success, returns a StarAmount object.

#### getStarTransactions

Returns the bot's Telegram Star transactions in chronological order. On success, returns a StarTransactions object.

#### refundStarPayment

Refunds a successful payment in Telegram Stars. Returns True on success.

#### editUserStarSubscription

Allows the bot to cancel or re-enable extension of a subscription paid in Telegram Stars. Returns True on success.

#### LabeledPrice

This object represents a portion of the price for goods or services.

#### Invoice

This object contains basic information about an invoice.

#### ShippingAddress

This object represents a shipping address.

#### OrderInfo

This object represents information about an order.

#### ShippingOption

This object represents one shipping option.

#### SuccessfulPayment

This object contains basic information about a successful payment. Note that if the buyer initiates a chargeback with the relevant payment provider following this transaction, the funds may be debited from your balance. This is outside of Telegram's control.

#### RefundedPayment

This object contains basic information about a refunded payment.

#### ShippingQuery

This object contains information about an incoming shipping query.

#### PreCheckoutQuery

This object contains information about an incoming pre-checkout query.

#### PaidMediaPurchased

This object contains information about a paid media purchase.

#### RevenueWithdrawalState

This object describes the state of a revenue withdrawal operation. Currently, it can be one of

- RevenueWithdrawalStatePending

- RevenueWithdrawalStateSucceeded

- RevenueWithdrawalStateFailed

#### RevenueWithdrawalStatePending

The withdrawal is in progress.

#### RevenueWithdrawalStateSucceeded

The withdrawal succeeded.

#### RevenueWithdrawalStateFailed

The withdrawal failed and the transaction was refunded.

#### AffiliateInfo

Contains information about the affiliate that received a commission via this transaction.

#### TransactionPartner

This object describes the source of a transaction, or its recipient for outgoing transactions. Currently, it can be one of

- TransactionPartnerUser

- TransactionPartnerChat

- TransactionPartnerAffiliateProgram

- TransactionPartnerFragment

- TransactionPartnerTelegramAds

- TransactionPartnerTelegramApi

- TransactionPartnerOther

#### TransactionPartnerUser

Describes a transaction with a user.

#### TransactionPartnerChat

Describes a transaction with a chat.

#### TransactionPartnerAffiliateProgram

Describes the affiliate program that issued the affiliate commission received via this transaction.

#### TransactionPartnerFragment

Describes a withdrawal transaction with Fragment.

#### TransactionPartnerTelegramAds

Describes a withdrawal transaction to the Telegram Ads platform.

#### TransactionPartnerTelegramApi

Describes a transaction with payment for paid broadcasting.

#### TransactionPartnerOther

Describes a transaction with an unknown source or recipient.

#### StarTransaction

Describes a Telegram Star transaction. Note that if the buyer initiates a chargeback with the payment provider from whom they acquired Stars (e.g., Apple, Google) following this transaction, the refunded Stars will be deducted from the bot's balance. This is outside of Telegram's control.

#### StarTransactions

Contains a list of Telegram Star transactions.

### Telegram Passport

Telegram Passport is a unified authorization method for services that require personal identification. Users can upload their documents once, then instantly share their data with services that require real-world ID (finance, ICOs, etc.). Please see the manual for details.

#### PassportData

Describes Telegram Passport data shared with the bot by the user.

#### PassportFile

This object represents a file uploaded to Telegram Passport. Currently all Telegram Passport files are in JPEG format when decrypted and don't exceed 10MB.

#### EncryptedPassportElement

Describes documents or other Telegram Passport elements shared with the bot by the user.

#### EncryptedCredentials

Describes data required for decrypting and authenticating EncryptedPassportElement. See the Telegram Passport Documentation for a complete description of the data decryption and authentication processes.

#### setPassportDataErrors

Informs a user that some of the Telegram Passport elements they provided contains errors. The user will not be able to re-submit their Passport to you until the errors are fixed (the contents of the field for which you returned the error must change). Returns True on success.

Use this if the data submitted by the user doesn't satisfy the standards your service requires for any reason. For example, if a birthday date seems invalid, a submitted document is blurry, a scan shows evidence of tampering, etc. Supply some details in the error message to make sure the user knows how to correct the issues.

#### PassportElementError

This object represents an error in the Telegram Passport element which was submitted that should be resolved by the user. It should be one of:

- PassportElementErrorDataField

- PassportElementErrorFrontSide

- PassportElementErrorReverseSide

- PassportElementErrorSelfie

- PassportElementErrorFile

- PassportElementErrorFiles

- PassportElementErrorTranslationFile

- PassportElementErrorTranslationFiles

- PassportElementErrorUnspecified

#### PassportElementErrorDataField

Represents an issue in one of the data fields that was provided by the user. The error is considered resolved when the field's value changes.

#### PassportElementErrorFrontSide

Represents an issue with the front side of a document. The error is considered resolved when the file with the front side of the document changes.

#### PassportElementErrorReverseSide

Represents an issue with the reverse side of a document. The error is considered resolved when the file with reverse side of the document changes.

#### PassportElementErrorSelfie

Represents an issue with the selfie with a document. The error is considered resolved when the file with the selfie changes.

#### PassportElementErrorFile

Represents an issue with a document scan. The error is considered resolved when the file with the document scan changes.

#### PassportElementErrorFiles

Represents an issue with a list of scans. The error is considered resolved when the list of files containing the scans changes.

#### PassportElementErrorTranslationFile

Represents an issue with one of the files that constitute the translation of a document. The error is considered resolved when the file changes.

#### PassportElementErrorTranslationFiles

Represents an issue with the translated version of a document. The error is considered resolved when a file with the document translation change.

#### PassportElementErrorUnspecified

Represents an issue in an unspecified place. The error is considered resolved when new data is added.

### Games

Your bot can offer users HTML5 games to play solo or to compete against each other in groups and one-on-one chats. Create games via @BotFather using the /newgame command. Please note that this kind of power requires responsibility: you will need to accept the terms for each game that your bots will be offering.

- Games are a new type of content on Telegram, represented by the Game and InlineQueryResultGame objects.

- Once you've created a game via BotFather, you can send games to chats as regular messages using the sendGame method, or use inline mode with InlineQueryResultGame.

- If you send the game message without any buttons, it will automatically have a 'Play GameName' button. When this button is pressed, your bot gets a CallbackQuery with the game_short_name of the requested game. You provide the correct URL for this particular user and the app opens the game in the in-app browser.

- You can manually add multiple buttons to your game message. Please note that the first button in the first row must always launch the game, using the field callback_game in InlineKeyboardButton. You can add extra buttons according to taste: e.g., for a description of the rules, or to open the game's official community.

- To make your game more attractive, you can upload a GIF animation that demonstrates the game to the users via BotFather (see Lumberjack for example).

- A game message will also display high scores for the current chat. Use setGameScore to post high scores to the chat with the game, add the disable_edit_message parameter to disable automatic update of the message with the current scoreboard.

- Use getGameHighScores to get data for in-game high score tables.

- You can also add an extra sharing button for users to share their best score to different chats.

- For examples of what can be done using this new stuff, check the @gamebot and @gamee bots.

#### sendGame

Use this method to send a game. On success, the sent Message is returned.

#### Game

This object represents a game. Use BotFather to create and edit games, their short names will act as unique identifiers.

#### CallbackGame

A placeholder, currently holds no information. Use BotFather to set up your game.

#### setGameScore

Use this method to set the score of the specified user in a game message. On success, if the message is not an inline message, the Message is returned, otherwise True is returned. Returns an error, if the new score is not greater than the user's current score in the chat and force is False.

#### getGameHighScores

Use this method to get data for high score tables. Will return the score of the specified user and several of their neighbors in a game. Returns an Array of GameHighScore objects.

> This method will currently return scores for the target user, plus two of their closest neighbors on each side. Will also return the top three users if the user and their neighbors are not among them. Please note that this behavior is subject to change.

#### GameHighScore

This object represents one row of the high scores table for a game.

---

And that's about all we've got for now.If you've got any questions, please check out our Bot FAQ »

