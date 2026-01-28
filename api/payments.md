# Payments API

You can accept payments from Telegram users via Telegram Bots.

> Note: This article is intended for MTProto API developers. If you're looking for a general overview of Telegram Payments, check out the Telegram blog and the bot API payment manual.

### Introducing Payments

Telegram bots can accept payments for goods and services from users.
For more info on how payments work, check out the Telegram Blog and the bot API payment manual.

This page will elaborate on the actions required to work with payments using the MTProto API.

> A simplified version of the process is available only for bots using the bot API.

The first step for bots is enable payments as described here ».

Then, we work with payments as follows.

### 1. Create Invoice

#### 1.1 Create Invoice Message

```
inputWebDocument#9bed434d url:string size:int mime_type:string attributes:Vector<DocumentAttribute> = InputWebDocument;

labeledPrice#cb296bf8 label:string amount:long = LabeledPrice;

invoice#49ee584 flags:# test:flags.0?true name_requested:flags.1?true phone_requested:flags.2?true email_requested:flags.3?true shipping_address_requested:flags.4?true flexible:flags.5?true phone_to_provider:flags.6?true email_to_provider:flags.7?true recurring:flags.9?true currency:string prices:Vector<LabeledPrice> max_tip_amount:flags.8?long suggested_tip_amounts:flags.8?Vector<long> terms_url:flags.10?string subscription_period:flags.11?int = Invoice;

inputMediaInvoice#405fef0d flags:# title:string description:string photo:flags.0?InputWebDocument invoice:Invoice payload:bytes provider:flags.3?string provider_data:DataJSON start_param:flags.1?string extended_media:flags.2?InputMedia = InputMedia;

---functions---

messages.sendMedia#ac55d9c1 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;
```

The user contacts the bot and requests to purchase something.
The bot forms an inputMediaInvoice with an invoice constructor with a description of the goods or service, amount to be paid, as well as requested shipping info.
The provider parameter of the inputMediaInvoice constructor is where you put the token value that you've obtained earlier via Botfather. It is possible for one merchant bot to use several different tokens for different users or different goods and services.

Use the messages.sendMedia method to send the invoice. 
You can also attach an inline keyboard to the message using the reply_markup field: if provided, the first button must be a keyboardButtonBuy button. Otherwise, an inline keyboard will be generated automatically, with a Pay 'total price' keyboardButtonBuy as only button.

An invoice message with a pay button can only be sent to a private chat with the user. Groups and channels are not supported.

#### 1.2 Create Invoice Link

```
inputMediaInvoice#405fef0d flags:# title:string description:string photo:flags.0?InputWebDocument invoice:Invoice payload:bytes provider:flags.3?string provider_data:DataJSON start_param:flags.1?string extended_media:flags.2?InputMedia = InputMedia;

payments.exportedInvoice#aed0cbd9 url:string = payments.ExportedInvoice;

---functions---

payments.exportInvoice#f91b065 invoice_media:InputMedia = payments.ExportedInvoice;
```

Bots may also generate invoice deep links using payments.exportInvoice.

The returned payments.exportedInvoice will contain an invoice deep link that can be shared directly, or sent in a bot mini app web_app_open_invoice event.

### 2. Order information

#### 2.1 Invoice

```
keyboardButtonBuy#afd93fbb text:string = KeyboardButton;

keyboardButtonRow#77608b83 buttons:Vector<KeyboardButton> = KeyboardButtonRow;
replyInlineMarkup#48a30254 rows:Vector<KeyboardButtonRow> = ReplyMarkup;

webDocument#1c570ed1 url:string access_hash:long size:int mime_type:string attributes:Vector<DocumentAttribute> = WebDocument;
webDocumentNoProxy#f9c8bcc6 url:string size:int mime_type:string attributes:Vector<DocumentAttribute> = WebDocument;

messageMediaInvoice#f6a548d3 flags:# shipping_address_requested:flags.1?true test:flags.3?true title:string description:string photo:flags.0?WebDocument receipt_msg_id:flags.2?int currency:string total_amount:long start_param:string extended_media:flags.4?MessageExtendedMedia = MessageMedia;

message#9815cec8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true from_scheduled:flags.18?true legacy:flags.19?true edit_hide:flags.21?true pinned:flags.24?true noforwards:flags.26?true invert_media:flags.27?true flags2:# offline:flags2.1?true video_processing_pending:flags2.4?true paid_suggested_post_stars:flags2.8?true paid_suggested_post_ton:flags2.9?true id:int from_id:flags.8?Peer from_boosts_applied:flags.29?int peer_id:Peer saved_peer_id:flags.28?Peer fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long via_business_bot_id:flags2.0?long reply_to:flags.3?MessageReplyHeader date:int message:string media:flags.9?MessageMedia reply_markup:flags.6?ReplyMarkup entities:flags.7?Vector<MessageEntity> views:flags.10?int forwards:flags.10?int replies:flags.23?MessageReplies edit_date:flags.15?int post_author:flags.16?string grouped_id:flags.17?long reactions:flags.20?MessageReactions restriction_reason:flags.22?Vector<RestrictionReason> ttl_period:flags.25?int quick_reply_shortcut_id:flags.30?int effect:flags2.2?long factcheck:flags2.3?FactCheck report_delivery_until_date:flags2.5?int paid_message_stars:flags2.6?long suggested_post:flags2.7?SuggestedPost = Message;

updateNewMessage#1f2b0afd message:Message pts:int pts_count:int = Update;
```

The user receives an invoice deep link or an updateNewMessage constructor from the bot, containing a messageMediaInvoice constructor with basic info about the product.

For invoice messages, the message will also have a replyInlineMarkup keyboard attached to it.
The first button of the keyboard will always be a keyboardButtonBuy button.

Pass XTR as currency to request payment in Telegram Stars.

#### 2.2 Getting invoice info about the product

```
inputStorePaymentPremiumGiveaway#160544ca flags:# only_new_subscribers:flags.0?true winners_are_visible:flags.3?true boost_peer:InputPeer additional_peers:flags.1?Vector<InputPeer> countries_iso2:flags.2?Vector<string> prize_description:flags.4?string random_id:long until_date:int currency:string amount:long = InputStorePaymentPurpose;
inputStorePaymentPremiumGiftCode#fb790393 flags:# users:Vector<InputUser> boost_peer:flags.0?InputPeer currency:string amount:long message:flags.1?TextWithEntities = InputStorePaymentPurpose;

inputInvoiceMessage#c5b56859 peer:InputPeer msg_id:int = InputInvoice;
inputInvoiceSlug#c326caef slug:string = InputInvoice;
inputInvoicePremiumGiftCode#98986c0d purpose:InputStorePaymentPurpose option:PremiumGiftCodeOption = InputInvoice;
inputInvoiceStars#65f00ce3 purpose:InputStorePaymentPurpose = InputInvoice;
inputInvoiceChatInviteSubscription#34e793f1 hash:string = InputInvoice;
inputInvoiceStarGift#e8625e92 flags:# hide_name:flags.0?true include_upgrade:flags.2?true peer:InputPeer gift_id:long message:flags.1?TextWithEntities = InputInvoice;
inputInvoiceStarGiftUpgrade#4d818d5d flags:# keep_original_details:flags.0?true stargift:InputSavedStarGift = InputInvoice;
inputInvoiceStarGiftPrepaidUpgrade#9a0b48b8 peer:InputPeer hash:string = InputInvoice;
inputInvoiceStarGiftTransfer#4a5f5bd9 stargift:InputSavedStarGift to_id:InputPeer = InputInvoice;
inputInvoicePremiumGiftStars#dabab2ef flags:# user_id:InputUser months:int message:flags.0?TextWithEntities = InputInvoice;
inputInvoiceBusinessBotTransferStars#f4997e42 bot:InputUser stars:long = InputInvoice;
inputInvoiceStarGiftResale#c39f5324 flags:# ton:flags.0?true slug:string to_id:InputPeer = InputInvoice;

invoice#49ee584 flags:# test:flags.0?true name_requested:flags.1?true phone_requested:flags.2?true email_requested:flags.3?true shipping_address_requested:flags.4?true flexible:flags.5?true phone_to_provider:flags.6?true email_to_provider:flags.7?true recurring:flags.9?true currency:string prices:Vector<LabeledPrice> max_tip_amount:flags.8?long suggested_tip_amounts:flags.8?Vector<long> terms_url:flags.10?string subscription_period:flags.11?int = Invoice;

paymentRequestedInfo#909c3f94 flags:# name:flags.0?string phone:flags.1?string email:flags.2?string shipping_address:flags.3?PostAddress = PaymentRequestedInfo;

paymentSavedCredentialsCard#cdc27a1f id:string title:string = PaymentSavedCredentials;

payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;

payments.paymentFormStars#7bf6b15c flags:# form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice users:Vector<User> = payments.PaymentForm;
payments.paymentFormStarGift#b425cfe1 form_id:long invoice:Invoice = payments.PaymentForm;

---functions---

payments.getPaymentForm#37148dbb flags:# invoice:InputInvoice theme_params:flags.0?DataJSON = payments.PaymentForm;
```

payments.getPaymentForm is used to return a payment form from an invoice, providing the following invoice parameter:

- inputInvoiceMessage, used:

- If the user clicks on the keyboardButtonBuy button, contains the message ID of the invoice preview message.

- When purchasing paid media ».

- inputInvoiceSlug

- If the user opens an invoice deep link, contains the slug parameter

- If the client has to process a Telegram Premium payment, contains the premium_invoice_slug app config parameter »

- inputInvoicePremiumGiftCode

- Used if the user wishes to start a channel giveaway or send some giftcodes to members of a channel, in exchange for boosts.

- The purpose field should be populated with inputStorePaymentPremiumGiveaway for giveaways and inputStorePaymentPremiumGiftCode for gifts.

- The option field should be populated with one of the giveaway options returned by payments.getPremiumGiftCodeOptions.

- See the giveaways » documentation for more info.

- inputInvoiceStars

- Used to purchase Telegram Stars.

- The option field should be populated with one of the star topup options returned by payments.getStarsTopupOptions.

- See the stars » documentation for more info.

- inputInvoiceChatInviteSubscription

- Used to implement bot and channel subscriptions ».

- See the subscriptions » documentation for more info.

- inputInvoiceStarGift

- Used to purchase Telegram Star Gifts.

- See the gifts » documentation for more info.

- inputInvoiceStarGiftUpgrade

- Used to pay to upgrade a Gift to a collectible gift.

- See the collectible gifts » documentation for more info.

- inputInvoiceStarGiftPrepaidUpgrade

- Used to pay for someone to upgrade a Gift to a collectible gift.

- See the collectible gifts » documentation for more info.

- inputInvoiceStarGiftTransfer

- Used to pay to transfer a Gift to another peer.

- See the gifts » documentation for more info.

- inputInvoiceStarGiftResale

- Used to to buy a Gift on resale.

- See the gifts » documentation for more info.

- inputInvoicePremiumGiftStars

- Used to gift a Premium subscription to another user, paying with Telegram Stars.

- See the Telegram Premium » documentation for more info

- inputInvoiceBusinessBotTransferStars

- Used to transfer Telegram Stars from the balance of a user controlled by a business bot, to the bot's balance.

- See the Telegram Business » documentation for more info.

The returned form will contain fields that should be passed to the payment provider along with the full invoice.
The payment form also contains info about previously saved payment credentials and order information (name, phone number, email, shipping address & so on).

The full invoice contains info about the information required for the order, the price and the currency, and whether this is a test order.
The recurring flag will be set for recurring payments, and recurring_terms_url will link to the terms of service of the recurring payment: the user must read and accept them before continuing.

A payments.paymentFormStars/payments.paymentFormStarGift will be returned if the payment is to be made using Telegram Stars, see here » for more info (note that this constructor is used for payments in Telegram Stars to bots and peers, it will not be returned when topping up the Telegram Star balance of the current account using inputInvoiceStars): the associated invoice will use XTR as currency.

#### 2.3 Verifying information

```
invoice#49ee584 flags:# test:flags.0?true name_requested:flags.1?true phone_requested:flags.2?true email_requested:flags.3?true shipping_address_requested:flags.4?true flexible:flags.5?true phone_to_provider:flags.6?true email_to_provider:flags.7?true recurring:flags.9?true currency:string prices:Vector<LabeledPrice> max_tip_amount:flags.8?long suggested_tip_amounts:flags.8?Vector<long> terms_url:flags.10?string subscription_period:flags.11?int = Invoice;

postAddress#1e8caaeb street_line1:string street_line2:string city:string state:string country_iso2:string post_code:string = PostAddress;

paymentRequestedInfo#909c3f94 flags:# name:flags.0?string phone:flags.1?string email:flags.2?string shipping_address:flags.3?PostAddress = PaymentRequestedInfo;

payments.validatedRequestedInfo#d1451883 flags:# id:flags.0?string shipping_options:flags.1?Vector<ShippingOption> = payments.ValidatedRequestedInfo;

---functions---

payments.validateRequestedInfo#b6c8f12b flags:# save:flags.0?true invoice:InputInvoice info:PaymentRequestedInfo = payments.ValidatedRequestedInfo;
```

If any data at all is requested by the invoice (name_requested, phone_requested, email_requested, shipping_address_requested), the user must call payments.validateRequestedInfo, providing the required data (as usual, msg_id is the ID of the invoice message).
The user can choose to save order information for future use by setting the save flag.
Data can be autofilled as described in autofill.

If no errors are found in the submitted info, the response of the method will contain an id flag, to be used later to complete the payment.

If the flexible flag of the invoice is set, calling the payments.validateRequestedInfo method will send a shipping query update to the bot, to which the bot will reply with the available shipping options for the specified address as described here ».
The return value in this case will also contain a shipping_options field with the available shipping options.

If any errors are found in the submitted data, a service notification will be sent to the user, with a description of the error from the bot.

#### 2.3.1 Autofill

```
payments.savedInfo#fb8fe43c flags:# has_saved_credentials:flags.1?true saved_info:flags.0?PaymentRequestedInfo = payments.SavedInfo;

---functions---

payments.getSavedInfo#227d824b = payments.SavedInfo;
payments.clearSavedInfo#d83d70c1 flags:# credentials:flags.0?true info:flags.1?true = Bool;
```

The requested fields can be autofilled with the info provided in the saved_info field of the payment form, or with the info fetched manually using payments.getSavedInfo.

Saved order information can also be cleared using payments.clearSavedInfo.

#### 2.4 Select delivery option

```
labeledPrice#cb296bf8 label:string amount:long = LabeledPrice;

shippingOption#b6213cdf id:string title:string prices:Vector<LabeledPrice> = ShippingOption;

updateBotShippingQuery#b5aefd7d query_id:long user_id:long payload:bytes shipping_address:PostAddress = Update;

---functions---

messages.setBotShippingResults#e5f672fa flags:# query_id:long error:flags.0?string shipping_options:flags.1?Vector<ShippingOption> = Bool;
```

If a shipping address was requested and the bot included the parameter flexible, when the user validates order information the Telegram API will send an updateBotShippingQuery to the bot. 
The bot must respond using messages.setBotShippingResults either with a list of possible delivery options and the relevant delivery prices, or with an error (for example, if delivery to the specified address is not possible).

The returned shipping options or the shipping error will be returned to the user while validating order information.

### 3. Payment

#### 3.1 Star payment

```
payments.paymentFormStars#7bf6b15c flags:# form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice users:Vector<User> = payments.PaymentForm;
payments.paymentFormStarGift#b425cfe1 form_id:long invoice:Invoice = payments.PaymentForm;

---functions---

payments.sendStarsForm#7998c914 form_id:long invoice:InputInvoice = payments.PaymentResult;
```

A payments.paymentFormStars or payments.paymentFormStarGift will be returned if the payment should be made using Telegram Stars, invoking payments.sendStarsForm instead of payments.sendPaymentForm at step 4 ».

Calling payments.sendStarsForm twice with the same form_id will not repeat the transaction.

Note that the returned form is only valid for 10 minutes, after which a call to payments.sendStarsForm will return a 400 FORM_EXPIRED error.
When receiving this error, simply re-generate the form as specified in step 2.2 » and re-call payments.sendStarsForm.

A 400 BALANCE_TOO_LOW error will be emitted by payments.sendStarsForm if the current Telegram Stars balance is not enough to complete the transaction: when receiving this error, the client should invite the user to topup their Telegram Stars balance », before re-invoking payments.sendStarsForm.

#### 3.2 Web payment

```
inputPaymentCredentials#3417d728 flags:# save:flags.0?true data:DataJSON = InputPaymentCredentials;

payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;

paymentFormMethod#88f8f21b url:string title:string = PaymentFormMethod;
```

The user can choose to use either the main payment platform, using the url of the payments.paymentForm, or any of the additional payment platforms, using the url of the chosen paymentFormMethod.
Payment takes place by opening the url of the chosen payment platform in the specified payment form, which leads to a payment form on the website of the payment gateway.
Once the user finishes entering their payment credentials, a payment_form_submit web event is generated by the payment gateway, containing credentials and title JSON fields.

The title is used by the client app to represent the payment credentials (typically a censored version of credit card information).
The credentials are used to generate an inputPaymentCredentials constructor.
Eventually, you can set the save flag to save the credit card info for future use, only if 2FA is enabled.

Telegram does not have access to your card information. Credit card details will be handled only by the payment system.

#### 3.3 Native payment

```
inputPaymentCredentials#3417d728 flags:# save:flags.0?true data:DataJSON = InputPaymentCredentials;

payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;
```

Most telegram apps support working natively with the native APIs of some payment providers, without opening the website of the payment and receiving a JS event.

This is done using the JSON native_params parameters field of the payments.paymentForm constructor, which contains an object, which can contain one or more of the following fields:

- publishable_key: Stripe API publishable key

- apple_pay_merchant_id: Apple Pay merchant ID

- android_pay_public_key: Android Pay public key

- android_pay_bgcolor: Android Pay form background color

- android_pay_inverse: Whether to use the dark theme in the Android Pay form

- need_country: True, if the user country must be provided,

- need_zip: True, if the user ZIP/postal code must be provided,

- need_cardholder_name: True, if the cardholder name must be provided

The payment gateway to use is decided based on the value of the native_provider field.

##### 3.3.1 Stripe

```
inputPaymentCredentials#3417d728 flags:# save:flags.0?true data:DataJSON = InputPaymentCredentials;

payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;
```

If the native_provider field is set and equal to stripe, the client can make use of the native Stripe token APIs with the publishable_key from the native_params to add a payment method to Stripe, and then use the token type and id to generate a JSON object:

```
{"type":"token.type", "id":"token.id"}"
```

The generated JSON object can then be passed to the data field of the inputPaymentCredentials.
Eventually, you can set the save flag to save the credit card info for future use, only if 2FA is enabled.

Telegram does not have access to your card information. Credit card details will be handled only by the payment system.

Example implementation: Telegram for Android.

#### 3.4 Apple pay

```
inputPaymentCredentialsApplePay#aa1c39f payment_data:DataJSON = InputPaymentCredentials;
```

On iOS devices, Apple Pay can be used to generate payment data, which is then sent using the inputPaymentCredentialsApplePay constructor.

Example implementation: Telegram for iOS.

#### 3.5 Android pay

```
inputPaymentCredentialsGooglePay#8ac32801 payment_token:DataJSON = InputPaymentCredentials;
```

On Android devices, Google Pay can be used to generate payment data, which is then sent using the inputPaymentCredentialsGooglePay constructor.

Example implementation: Telegram for Android.

#### 3.6 Using saved payment credentials

```
inputPaymentCredentialsSaved#c10eb2cf id:string tmp_password:bytes = InputPaymentCredentials;

paymentSavedCredentialsCard#cdc27a1f id:string title:string = PaymentSavedCredentials;

payments.paymentForm#a0058751 flags:# can_save_credentials:flags.2?true password_missing:flags.3?true form_id:long bot_id:long title:string description:string photo:flags.5?WebDocument invoice:Invoice provider_id:long url:string native_provider:flags.4?string native_params:flags.4?DataJSON additional_methods:flags.6?Vector<PaymentFormMethod> saved_info:flags.0?PaymentRequestedInfo saved_credentials:flags.1?Vector<PaymentSavedCredentials> users:Vector<User> = payments.PaymentForm;

account.tmpPassword#db64fd34 tmp_password:bytes valid_until:int = account.TmpPassword;

---functions---

account.getTmpPassword#449e0b51 password:InputCheckPasswordSRP period:int = account.TmpPassword;
```

To reuse saved payment methods, the saved_credentials field of the payment form is used.
The title of the paymentSavedCredentialsCard can be used to preview a censored version of credit card info.
The id field is provided by the payment provider directly to the Telegram servers when saving the payment method, and identifies the payment method.
Full credit card info is not saved on Telegram Servers, and cannot be fetched by the user.

In order to use the saved payment method, 2FA must be enabled: the user must verify their identity by entering their 2FA password, which is then used as described in the SRP docs to generate SRP parameters which must be passed to account.getTmpPassword.

The generated temporary password can then be used to make payments using the saved credentials using the inputPaymentCredentialsSaved constructor.

- The id field is the paymentSavedCredentialsCard id.

- The tmp_password is the temporary payment password generated by the server, if the user provided a correct 2FA password.

Example implementation: Telegram for Android.

### 4. Pre-Checkout

```
inputPaymentCredentialsSaved#c10eb2cf id:string tmp_password:bytes = InputPaymentCredentials;
inputPaymentCredentials#3417d728 flags:# save:flags.0?true data:DataJSON = InputPaymentCredentials;
inputPaymentCredentialsApplePay#aa1c39f payment_data:DataJSON = InputPaymentCredentials;
inputPaymentCredentialsGooglePay#8ac32801 payment_token:DataJSON = InputPaymentCredentials;

payments.paymentResult#4e5f810d updates:Updates = payments.PaymentResult;
payments.paymentVerificationNeeded#d8411139 url:string = payments.PaymentResult;

---functions---

payments.sendPaymentForm#2d03522f flags:# form_id:long invoice:InputInvoice requested_info_id:flags.0?string shipping_option_id:flags.1?string credentials:InputPaymentCredentials tip_amount:flags.2?long = payments.PaymentResult;

payments.sendStarsForm#7998c914 form_id:long invoice:InputInvoice = payments.PaymentResult;
```

After verifying order information, the final step for the client is to call payments.sendPaymentForm or payments.sendStarsForm for payments using Telegram Stars », with the following parameters:

- The form_id is set to the ID of the form

- The invoice is set to the previously passed invoice

- requested_info_id is set to the id of the verified order information, if it was requested

- shipping_option_id is set to the selected delivery option, if shipping was requested.

- credentials are the payment credentials generated by the payment provider, required to complete the order.

Payment method info can also be saved to the Telegram Servers and reused, by setting the save flag of inputPaymentCredentials when sending the form.
This is only possible on accounts with 2FA enabled.

The bot then replies to the received precheckout query, finally the user proceeds to checkout.

Please note that if the result of the method is a payments.paymentVerificationNeeded, before proceeding to checkout the payment provider requires the user to verify their identity by opening the provided url and following instructions (ie 3-D Secure).
Once the user finishes working with the webpage, the client can proceed to checkout.

Eventual errors are returned in the form of RPC errors (rpc_error), with the description of the error by the bot contained in additional service updates received separately, see here for more info.

Note that eventual payment errors will not be sent to the client via MTProto if they occur during additional verification (if a payments.paymentVerificationNeeded is returned and the user fails TOTP verification): such errors will only be displayed inside of the verification webview, no MTProto updates or RPC errors (rpc_error) will be received.

#### 4.1 Receiving pre-checkout query

```
paymentRequestedInfo#909c3f94 flags:# name:flags.0?string phone:flags.1?string email:flags.2?string shipping_address:flags.3?PostAddress = PaymentRequestedInfo;

updateBotPrecheckoutQuery#8caa9a96 flags:# query_id:long user_id:long payload:bytes info:flags.0?PaymentRequestedInfo shipping_option_id:flags.1?string currency:string total_amount:long = Update;

---functions---

messages.setBotPrecheckoutResults#9c2dd95 flags:# success:flags.1?true query_id:long error:flags.0?string = Bool;
```

The user enters their payment information as described above and presses the final pay button.
At this moment the Telegram API sends an updateBotPrecheckoutQuery constructor that contains all the available information about the order to the bot. 
The bot must reply using messages.setBotPrecheckoutResults within 10 seconds after receiving this update or the transaction is canceled.

The bot may return an error if it can't process the order for any reason. We highly recommend specifying a reason for failure to complete the order in human readable form (e.g. "Sorry, we're all out of rubber ducks! Would you be interested in a steel bear instead?"). Telegram will display this reason to the user.

### 5. Checkout

```
keyboardButtonBuy#afd93fbb text:string = KeyboardButton;

keyboardButtonRow#77608b83 buttons:Vector<KeyboardButton> = KeyboardButtonRow;
replyInlineMarkup#48a30254 rows:Vector<KeyboardButtonRow> = ReplyMarkup;

messageMediaInvoice#f6a548d3 flags:# shipping_address_requested:flags.1?true test:flags.3?true title:string description:string photo:flags.0?WebDocument receipt_msg_id:flags.2?int currency:string total_amount:long start_param:string extended_media:flags.4?MessageExtendedMedia = MessageMedia;

message#9815cec8 flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true silent:flags.13?true post:flags.14?true from_scheduled:flags.18?true legacy:flags.19?true edit_hide:flags.21?true pinned:flags.24?true noforwards:flags.26?true invert_media:flags.27?true flags2:# offline:flags2.1?true video_processing_pending:flags2.4?true paid_suggested_post_stars:flags2.8?true paid_suggested_post_ton:flags2.9?true id:int from_id:flags.8?Peer from_boosts_applied:flags.29?int peer_id:Peer saved_peer_id:flags.28?Peer fwd_from:flags.2?MessageFwdHeader via_bot_id:flags.11?long via_business_bot_id:flags2.0?long reply_to:flags.3?MessageReplyHeader date:int message:string media:flags.9?MessageMedia reply_markup:flags.6?ReplyMarkup entities:flags.7?Vector<MessageEntity> views:flags.10?int forwards:flags.10?int replies:flags.23?MessageReplies edit_date:flags.15?int post_author:flags.16?string grouped_id:flags.17?long reactions:flags.20?MessageReactions restriction_reason:flags.22?Vector<RestrictionReason> ttl_period:flags.25?int quick_reply_shortcut_id:flags.30?int effect:flags2.2?long factcheck:flags2.3?FactCheck report_delivery_until_date:flags2.5?int paid_message_stars:flags2.6?long suggested_post:flags2.7?SuggestedPost = Message;

updateNewMessage#1f2b0afd message:Message pts:int pts_count:int = Update;

payments.paymentReceipt#70c4fe03 flags:# date:int bot_id:long provider_id:long title:string description:string photo:flags.2?WebDocument invoice:Invoice info:flags.0?PaymentRequestedInfo shipping:flags.1?ShippingOption tip_amount:flags.3?long currency:string total_amount:long credentials_title:string users:Vector<User> = payments.PaymentReceipt;

payments.paymentReceiptStars#dabbf83a flags:# date:int bot_id:long title:string description:string photo:flags.2?WebDocument invoice:Invoice currency:string total_amount:long transaction_id:string users:Vector<User> = payments.PaymentReceipt;

---functions---

payments.getPaymentReceipt#2478d1cc peer:InputPeer msg_id:int = payments.PaymentReceipt;
```

In case the bot confirms the order, Telegram requests the payment provider to complete the transaction. If the payment information was entered correctly and the payment goes through, the Telegram API will modify the invoice message and send a service message as described below. Once your bot receives this message, it should proceed with delivering the goods or services purchased by the user.

If all is OK, the user receives a payments.paymentResult in reply to the payments.sendPaymentForm query, containing info about the updated invoice message in the form of an updateEditMessage.

The invoice message will be updated as follows: the attached messageMediaInvoice will now have a receipt_msg_id field.
Clients should treat invoice messages with a receipt_msg_id field as receipt messages, locally modifying the label of the keyboardButtonBuy button to a localized version of the word Receipt.
From this point, clicking on the Receipt button should trigger a call to payments.getPaymentReceipt, providing the receipt_msg_id to the msg_id field, which will return info about the transaction.

The payment will also generate one service message of type messageActionPaymentSent or messageActionPaymentSentMe, replying to the invoice.
For bots, the service message will be of type messageActionPaymentSentMe, for users it will be a messageActionPaymentSent.
The recurring_init flag will be set if this payment also enables future recurring payments.
Further recurring payments will automatically send messageActionPaymentSentMe and messageActionPaymentSent messages with the recurring_used flag set.

```
messageActionPaymentSentMe#ffa00ccc flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long payload:bytes info:flags.0?PaymentRequestedInfo shipping_option_id:flags.1?string charge:PaymentCharge subscription_until_date:flags.4?int = MessageAction;
messageActionPaymentSent#c624b16e flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long invoice_slug:flags.0?string subscription_until_date:flags.4?int = MessageAction;
```

### 6. Refunds

```
paymentCharge#ea02c27e id:string provider_charge_id:string = PaymentCharge;

messageActionPaymentSentMe#ffa00ccc flags:# recurring_init:flags.2?true recurring_used:flags.3?true currency:string total_amount:long payload:bytes info:flags.0?PaymentRequestedInfo shipping_option_id:flags.1?string charge:PaymentCharge subscription_until_date:flags.4?int = MessageAction;

messageActionPaymentRefunded#41b3e202 flags:# peer:Peer currency:string total_amount:long payload:flags.0?bytes charge:PaymentCharge = MessageAction;

---functions---

payments.refundStarsCharge#25ae8f4a user_id:InputUser charge_id:string = Updates;
```

Payments made using Telegram Stars » may be refunded by the user/bot that received them by invoking payments.refundStarsCharge, passing to user_id the ID of the user that did the payment, and to charge_id the provider_charge_id from the messageActionPaymentSentMe service message action of the incoming payment.

This will emit a messageActionPaymentRefunded service message.

