# MessageAction
Object describing actions connected to a service message.

```
messageActionEmpty#b6aef7b0 = MessageAction;
messageActionChatCreate#bd47cbad title:string users:Vector<long> = MessageAction;
messageActionChatEditTitle#b5a1ce5a title:string = MessageAction;
messageActionChatEditPhoto#7fcb13a8 photo:Photo = MessageAction;
messageActionChatDeletePhoto#95e3fbef = MessageAction;
messageActionChatAddUser#15cefd00 users:Vector<long> = MessageAction;
messageActionChatDeleteUser#a43f30cc user_id:long = MessageAction;
messageActionChatJoinedByLink#31224c3 inviter_id:long = MessageAction;
messageActionChannelCreate#95d2ac92 title:string = MessageAction;
messageActionChatMigrateTo#e1037f92 channel_id:long = MessageAction;
messageActionChannelMigrateFrom#ea3948e9 title:string chat_id:long = MessageAction;
messageActionPinMessage#94bd38ed = MessageAction;
messageActionHistoryClear#9fbab604 = MessageAction;
messageActionGameScore#92a72876 game_id:long score:int = MessageAction;
messageActionPaymentSentMe#ffa00ccc flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long payload:bytes info:flags.0?PaymentRequestedInfo shipping_option_id:flags.1?string charge:PaymentCharge subscription_until_date:flags.4?int = MessageAction;
messageActionPaymentSent#c624b16e flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long invoice_slug:flags.0?string subscription_until_date:flags.4?int = MessageAction;
messageActionPhoneCall#80e11a7f flags:# video:flags.2?true call_id:long reason:flags.0?PhoneCallDiscardReason duration:flags.1?int = MessageAction;
messageActionScreenshotTaken#4792929b = MessageAction;
messageActionCustomAction#fae69f56 message:string = MessageAction;
messageActionBotAllowed#c516d679 flags:# attach_menu:flags.1?true from_request:flags.3?true domain:flags.0?string app:flags.2?BotApp = MessageAction;
messageActionSecureValuesSentMe#1b287353 values:Vector<SecureValue> credentials:SecureCredentialsEncrypted = MessageAction;
messageActionSecureValuesSent#d95c6154 types:Vector<SecureValueType> = MessageAction;
messageActionContactSignUp#f3f25f76 = MessageAction;
messageActionGeoProximityReached#98e0d697 from_id:Peer to_id:Peer distance:int = MessageAction;
messageActionGroupCall#7a0d7f42 flags:# call:InputGroupCall duration:flags.0?int = MessageAction;
messageActionInviteToGroupCall#502f92f7 call:InputGroupCall users:Vector<long> = MessageAction;
messageActionSetMessagesTTL#3c134d7b flags:# period:int auto_setting_from:flags.0?long = MessageAction;
messageActionGroupCallScheduled#b3a07661 call:InputGroupCall schedule_date:int = MessageAction;
messageActionSetChatTheme#b91bbd3a theme:ChatTheme = MessageAction;
messageActionChatJoinedByRequest#ebbca3cb = MessageAction;
messageActionWebViewDataSentMe#47dd8079 text:string data:string = MessageAction;
messageActionWebViewDataSent#b4c38cb5 text:string = MessageAction;
messageActionGiftPremium#6c6274fa flags:# currency:string amount:long months:int crypto_currency:flags.0?string crypto_amount:flags.0?long message:flags.1?TextWithEntities = MessageAction;
messageActionTopicCreate#d999256 flags:# title:string icon_color:int icon_emoji_id:flags.0?long = MessageAction;
messageActionTopicEdit#c0944820 flags:# title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = MessageAction;
messageActionSuggestProfilePhoto#57de635e photo:Photo = MessageAction;
messageActionRequestedPeer#31518e9b button_id:int peers:Vector<Peer> = MessageAction;
messageActionSetChatWallPaper#5060a3f4 flags:# same:flags.0?true for_both:flags.1?true wallpaper:WallPaper = MessageAction;
messageActionGiftCode#56d03994 flags:# via_giveaway:flags.0?true unclaimed:flags.5?true boost_peer:flags.1?Peer months:int slug:string currency:flags.2?string amount:flags.2?long crypto_currency:flags.3?string crypto_amount:flags.3?long message:flags.4?TextWithEntities = MessageAction;
messageActionGiveawayLaunch#a80f51e4 flags:# stars:flags.0?long = MessageAction;
messageActionGiveawayResults#87e2f155 flags:# stars:flags.0?true winners_count:int unclaimed_count:int = MessageAction;
messageActionBoostApply#cc02aa6d boosts:int = MessageAction;
messageActionRequestedPeerSentMe#93b31848 button_id:int peers:Vector<RequestedPeer> = MessageAction;
messageActionPaymentRefunded#41b3e202 flags:# peer:Peer currency:string total_amount:long payload:flags.0?bytes charge:PaymentCharge = MessageAction;
messageActionGiftStars#45d5b021 flags:# currency:string amount:long stars:long crypto_currency:flags.0?string crypto_amount:flags.0?long transaction_id:flags.1?string = MessageAction;
messageActionPrizeStars#b00c47a2 flags:# unclaimed:flags.0?true stars:long transaction_id:string boost_peer:Peer giveaway_msg_id:int = MessageAction;
messageActionStarGift#f24de7fa flags:# name_hidden:flags.0?true saved:flags.2?true converted:flags.3?true upgraded:flags.5?true refunded:flags.9?true can_upgrade:flags.10?true prepaid_upgrade:flags.13?true upgrade_separate:flags.16?true gift:StarGift message:flags.1?TextWithEntities convert_stars:flags.4?long upgrade_msg_id:flags.5?int upgrade_stars:flags.8?long from_id:flags.11?Peer peer:flags.12?Peer saved_id:flags.12?long prepaid_upgrade_hash:flags.14?string gift_msg_id:flags.15?int = MessageAction;
messageActionStarGiftUnique#34f762f3 flags:# upgrade:flags.0?true transferred:flags.1?true saved:flags.2?true refunded:flags.5?true prepaid_upgrade:flags.11?true gift:StarGift can_export_at:flags.3?int transfer_stars:flags.4?long from_id:flags.6?Peer peer:flags.7?Peer saved_id:flags.7?long resale_amount:flags.8?StarsAmount can_transfer_at:flags.9?int can_resell_at:flags.10?int = MessageAction;
messageActionPaidMessagesRefunded#ac1f1fcd count:int stars:long = MessageAction;
messageActionPaidMessagesPrice#84b88578 flags:# broadcast_messages_allowed:flags.0?true stars:long = MessageAction;
messageActionConferenceCall#2ffe2f7a flags:# missed:flags.0?true active:flags.1?true video:flags.4?true call_id:long duration:flags.2?int other_participants:flags.3?Vector<Peer> = MessageAction;
messageActionTodoCompletions#cc7c5c89 completed:Vector<int> incompleted:Vector<int> = MessageAction;
messageActionTodoAppendTasks#c7edbc83 list:Vector<TodoItem> = MessageAction;
messageActionSuggestedPostApproval#ee7a1596 flags:# rejected:flags.0?true balance_too_low:flags.1?true reject_comment:flags.2?string schedule_date:flags.3?int price:flags.4?StarsAmount = MessageAction;
messageActionSuggestedPostSuccess#95ddcf69 price:StarsAmount = MessageAction;
messageActionSuggestedPostRefund#69f916f8 flags:# payer_initiated:flags.0?true = MessageAction;
messageActionGiftTon#a8a3c699 flags:# currency:string amount:long crypto_currency:string crypto_amount:long transaction_id:flags.0?string = MessageAction;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messageActionEmpty | Empty constructor. |
| messageActionChatCreate | Group created |
| messageActionChatEditTitle | Group name changed. |
| messageActionChatEditPhoto | Group profile changed |
| messageActionChatDeletePhoto | Group profile photo removed. |
| messageActionChatAddUser | New member in the group |
| messageActionChatDeleteUser | User left the group. |
| messageActionChatJoinedByLink | A user joined the chat via an invite link |
| messageActionChannelCreate | The channel was created |
| messageActionChatMigrateTo | Indicates the chat was migrated to the specified supergroup |
| messageActionChannelMigrateFrom | Indicates the channel was migrated from the specified chat |
| messageActionPinMessage | A message was pinned |
| messageActionHistoryClear | Chat history was cleared |
| messageActionGameScore | Someone scored in a game |
| messageActionPaymentSentMe | A user just sent a payment to me (a bot) |
| messageActionPaymentSent | A payment was sent |
| messageActionPhoneCall | A phone call |
| messageActionScreenshotTaken | A screenshot of the chat was taken |
| messageActionCustomAction | Custom action (most likely not supported by the current layer, an upgrade might be needed) |
| messageActionBotAllowed | We have given the bot permission to send us direct messages.The optional fields specify how did we authorize the bot to send us messages. |
| messageActionSecureValuesSentMe | Secure telegram passport values were received |
| messageActionSecureValuesSent | Request for secure telegram passport values was sent |
| messageActionContactSignUp | A contact just signed up to telegram |
| messageActionGeoProximityReached | A user of the chat is now in proximity of another user |
| messageActionGroupCall | The group call has ended |
| messageActionInviteToGroupCall | A set of users was invited to the group call |
| messageActionSetMessagesTTL | The Time-To-Live of messages in this chat was changed. |
| messageActionGroupCallScheduled | A group call was scheduled |
| messageActionSetChatTheme | The chat theme was changed |
| messageActionChatJoinedByRequest | A user was accepted into the group by an admin |
| messageActionWebViewDataSentMe | Data from an opened reply keyboard bot mini app was relayed to the bot that owns it (bot side service message). |
| messageActionWebViewDataSent | Data from an opened reply keyboard bot mini app was relayed to the bot that owns it (user side service message).Clients should display a service message with the text Data from the «$text» button was transferred to the bot. |
| messageActionGiftPremium | Info about a gifted Telegram Premium subscriptionThis service message should be displayed below the appropriate sticker from the inputStickerSetPremiumGifts » stickerset »:- If months == 1, choose the sticker with emoji equal to ""- If months == 3, choose the sticker with emoji equal to ""- If months == 6, choose the sticker with emoji equal to ""- If months == 12, choose the sticker with emoji equal to ""- If months == 24, choose the sticker with emoji equal to ""- Otherwise, fallback to the sticker with emoji equal to "" |
| messageActionTopicCreate | A forum topic was created. |
| messageActionTopicEdit | Forum topic information was edited. |
| messageActionSuggestProfilePhoto | A new profile picture was suggested using photos.uploadContactProfilePhoto. |
| messageActionRequestedPeer | Contains info about one or more peers that the we (the user) shared with the bot after clicking on a keyboardButtonRequestPeer button (service message sent by the user). |
| messageActionSetChatWallPaper | The wallpaper » of the current chat was changed. |
| messageActionGiftCode | Contains a Telegram Premium giftcode link. |
| messageActionGiveawayLaunch | A giveaway was started. |
| messageActionGiveawayResults | A giveaway has ended. |
| messageActionBoostApply | Some boosts » were applied to the channel or supergroup. |
| messageActionRequestedPeerSentMe | Contains info about one or more peers that the a user shared with the me (the bot) after clicking on a keyboardButtonRequestPeer button (service message received by the bot). |
| messageActionPaymentRefunded | Describes a payment refund (service message received by both users and bots). |
| messageActionGiftStars | You gifted or were gifted some Telegram Stars.This service message should be displayed below the appropriate sticker from the inputStickerSetPremiumGifts » stickerset »:- If stars <= 1000, choose the sticker with emoji equal to ""- If stars < 2500, choose the sticker with emoji equal to ""- Otherwise, choose the sticker with emoji equal to "" |
| messageActionPrizeStars | You won some Telegram Stars in a Telegram Star giveaway ».This service message should be displayed below the appropriate sticker from the inputStickerSetPremiumGifts » stickerset »:- If stars <= 1000, choose the sticker with emoji equal to ""- If stars < 2500, choose the sticker with emoji equal to ""- Otherwise, choose the sticker with emoji equal to "" |
| messageActionStarGift | You received a gift, see here » for more info. |
| messageActionStarGiftUnique | A gift » was upgraded to a collectible gift ». |
| messageActionPaidMessagesRefunded | Sent from peer A to B, indicates that A refunded all stars B previously paid to send messages to A, see here » for more info on paid messages. |
| messageActionPaidMessagesPrice | The price of paid messages » in this chat was changed. |
| messageActionConferenceCall | Represents a conference call (or an invitation to a conference call, if neither the missed nor active flags are set).If call_requests_disabled is not set or false, an incoming messageActionConferenceCall with the missed and active flags not set should trigger ringing and an incoming call screen, just like for one-on-one calls. |
| messageActionTodoCompletions | Items were marked as completed or not completed in a todo list ». |
| messageActionTodoAppendTasks | Items were appended to the todo list ». |
| messageActionSuggestedPostApproval | A suggested post » was approved or rejected. |
| messageActionSuggestedPostSuccess | A suggested post » was successfully posted, and payment for it was successfully received. |
| messageActionSuggestedPostRefund | A suggested post » was accepted and posted or scheduled, but either the channel deleted the posted/scheduled post before stars_suggested_post_age_min seconds have elapsed, or the user refunded the payment for the stars used to pay for the suggested post. |
| messageActionGiftTon | You were gifted some toncoins.This service message should be displayed below the appropriate sticker from the inputStickerSetTonGifts » stickerset »:- If crypto_amount <= 10_000_000_000, choose the sticker with emoji equal to ""- If crypto_amount <= 50_000_000_000, choose the sticker with emoji equal to ""- Otherwise, choose the sticker with emoji equal to "" |


## Methods
| Method | Description |
| ---- | ----------- |


