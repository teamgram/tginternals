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
messageActionPaymentSentMe#8f31b327 flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long payload:bytes info:flags.0?PaymentRequestedInfo shipping_option_id:flags.1?string charge:PaymentCharge = MessageAction;
messageActionPaymentSent#96163f56 flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long invoice_slug:flags.0?string = MessageAction;
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
messageActionSetChatTheme#aa786345 emoticon:string = MessageAction;
messageActionChatJoinedByRequest#ebbca3cb = MessageAction;
messageActionWebViewDataSentMe#47dd8079 text:string data:string = MessageAction;
messageActionWebViewDataSent#b4c38cb5 text:string = MessageAction;
messageActionGiftPremium#c83d6aec flags:# currency:string amount:long months:int crypto_currency:flags.0?string crypto_amount:flags.0?long = MessageAction;
messageActionTopicCreate#d999256 flags:# title:string icon_color:int icon_emoji_id:flags.0?long = MessageAction;
messageActionTopicEdit#c0944820 flags:# title:flags.0?string icon_emoji_id:flags.1?long closed:flags.2?Bool hidden:flags.3?Bool = MessageAction;
messageActionSuggestProfilePhoto#57de635e photo:Photo = MessageAction;
messageActionRequestedPeer#31518e9b button_id:int peers:Vector<Peer> = MessageAction;
messageActionSetChatWallPaper#5060a3f4 flags:# same:flags.0?true for_both:flags.1?true wallpaper:WallPaper = MessageAction;
messageActionGiftCode#678c2e09 flags:# via_giveaway:flags.0?true unclaimed:flags.2?true boost_peer:flags.1?Peer months:int slug:string currency:flags.2?string amount:flags.2?long crypto_currency:flags.3?string crypto_amount:flags.3?long = MessageAction;
messageActionGiveawayLaunch#332ba9ed = MessageAction;
messageActionGiveawayResults#2a9fadc5 winners_count:int unclaimed_count:int = MessageAction;
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
| messageActionGiftPremium | Info about a gifted Telegram Premium subscription |
| messageActionTopicCreate | A forum topic was created. |
| messageActionTopicEdit | Forum topic information was edited. |
| messageActionSuggestProfilePhoto | A new profile picture was suggested using photos.uploadContactProfilePhoto. |
| messageActionRequestedPeer | Contains info about one or more peers that the user shared with the bot after clicking on a keyboardButtonRequestPeer button. |
| messageActionSetChatWallPaper | The wallpaper » of the current chat was changed. |
| messageActionGiftCode | Contains a Telegram Premium giftcode link. |
| messageActionGiveawayLaunch | A giveaway was started. |
| messageActionGiveawayResults | A giveaway has ended. |


## Methods
| Method | Description |
| ---- | ----------- |


