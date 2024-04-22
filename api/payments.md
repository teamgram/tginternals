# Payments API
You can accept payments from Telegram users via Telegram Bots.
> Note: This article is intended for MTProto API developers. If you're looking for a general overview of Telegram Payments, check out the Telegram blog and the bot API payment manual.
### Introducing Payments
Telegram bots can accept payments for goods and services from users.
For more info on how payments work, check out the Telegram Blog and the bot API payment manual.
This page will elaborate on the actions required to work with payments using the MTProto API.
> A simplified version of the process is available only for bots using the bot API.
The first step for bots is enable payments as described here ».
Then, we work with payments as follows.
### 1. Create Invoice
#### 1.1 Create Invoice Message
The user contacts the bot and requests to purchase something.
The bot forms an inputMediaInvoice with an invoice constructor with a description of the goods or service, amount to be paid, as well as requested shipping info.
The provider parameter of the inputMediaInvoice constructor is where you put the token value that you've obtained earlier via Botfather. It is possible for one merchant bot to use several different tokens for different users or different goods and services.
Use the messages.sendMedia method to send the invoice. 
You can also attach an inline keyboard to the message using the reply_markup field: if provided, the first button must be a keyboardButtonBuy button. Otherwise, an inline keyboard will be generated automatically, with a Pay 'total price' keyboardButtonBuy as only button.
An invoice message with a pay button can only be sent to a private chat with the user. Groups and channels are not supported.
#### 1.2 Create Invoice Link
Bots may also generate invoice deep links using payments.exportInvoice.
The returned payments.exportedInvoice will contain an invoice deep link that can be shared directly, or sent in a bot mini app web_app_open_invoice event.
### 2. Order information
#### 2.1 Invoice
The user receives an invoice deep link or an updateNewMessage constructor from the bot, containing a messageMediaInvoice constructor with basic info about the product.
For invoice messages, the message will also have a replyInlineMarkup keyboard attached to it.
The first button of the keyboard will always be a keyboardButtonBuy button.
#### 2.2 Getting invoice info about the product
payments.getPaymentForm is used to return a payment form from an invoice, providing the following invoice parameter:
- inputInvoiceMessage
- Used if the user clicks on the keyboardButtonBuy button, contains the message ID of the invoice preview message.
- inputInvoiceSlug
- If the user opens an invoice deep link, contains the slug parameter
- If the client has to process a Telegram Premium payment, contains the premium_invoice_slug app config parameter »
- inputInvoicePremiumGiftCode
- Used if the user wishes to start a channel giveaway or send some giftcodes to members of a channel, in exchange for boosts.
- The purpose field should be populated with inputStorePaymentPremiumGiveaway for giveaways and inputStorePaymentPremiumGiftCode for gifts.
- The option field should be populated with one of the giveaway options returned by payments.getPremiumGiftCodeOptions.
- See the giveaways » documentation for more info.
The returned form will contain fields that should be passed to the payment provider along with the full invoice.
The payment form also contains info about previously saved payment credentials and order information (name, phone number, email, shipping address & so on).
The full invoice contains info about the information required for the order, the price and the currency, and whether this is a test order.
The recurring flag will be set for recurring payments, and recurring_terms_url will link to the terms of service of the recurring payment: the user must read and accept them before continuing.
#### 2.3 Verifying information
If any data at all is requested by the invoice (name_requested, phone_requested, email_requested, shipping_address_requested), the user must call payments.validateRequestedInfo, providing the required data (as usual, msg_id is the ID of the invoice message).
The user can choose to save order information for future use by setting the save flag.
Data can be autofilled as described in autofill.
If no errors are found in the submitted info, the response of the method will contain an id flag, to be used later to complete the payment.
If the flexible flag of the invoice is set, calling the payments.validateRequestedInfo method will send a shipping query update to the bot, to which the bot will reply with the available shipping options for the specified address as described here ».
The return value in this case will also contain a shipping_options field with the available shipping options.
If any errors are found in the submitted data, a service notification will be sent to the user, with a description of the error from the bot.
#### 2.3.1 Autofill
The requested fields can be autofilled with the info provided in the saved_info field of the payment form, or with the info fetched manually using payments.getSavedInfo.
Saved order information can also be cleared using payments.clearSavedInfo.
#### 2.4 Select delivery option
If a shipping address was requested and the bot included the parameter flexible, when the user validates order information the Telegram API will send an updateBotShippingQuery to the bot. 
The bot must respond using messages.setBotShippingResults either with a list of possible delivery options and the relevant delivery prices, or with an error (for example, if delivery to the specified address is not possible).
The returned shipping options or the shipping error will be returned to the user while validating order information.
### 3. Payment
#### 3.1 Web payment
The user can choose to use either the main payment platform, using the url of the payments.paymentForm, or any of the additional payment platforms, using the url of the chosen paymentFormMethod.
Payment takes place by opening the url of the chosen payment platform in the specified payment form, which leads to a payment form on the website of the payment gateway.
Once the user finishes entering their payment credentials, a payment_form_submit web event is generated by the payment gateway, containing credentials and title JSON fields.
The title is used by the client app to represent the payment credentials (typically a censored version of credit card information).
The credentials are used to generate an inputPaymentCredentials constructor.
Eventually, you can set the save flag to save the credit card info for future use, only if 2FA is enabled.
Telegram does not have access to your card information. Credit card details will be handled only by the payment system.
#### 3.2 Native payment
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
##### 3.2.1 Stripe
If the native_provider field is set and equal to stripe, the client can make use of the native Stripe token APIs with the publishable_key from the native_params to add a payment method to Stripe, and then use the token type and id to generate a JSON object:
The generated JSON object can then be passed to the data field of the inputPaymentCredentials.
Eventually, you can set the save flag to save the credit card info for future use, only if 2FA is enabled.
Telegram does not have access to your card information. Credit card details will be handled only by the payment system.
Example implementation: Telegram for Android.
#### 3.3 Apple pay
On iOS devices, Apple Pay can be used to generate payment data, which is then sent using the inputPaymentCredentialsApplePay constructor.
Example implementation: Telegram for iOS.
#### 3.4 Android pay
On Android devices, Google Pay can be used to generate payment data, which is then sent using the inputPaymentCredentialsGooglePay constructor.
Example implementation: Telegram for Android.
#### 3.5 Using saved payment credentials
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
After verifying order information, the final step for the client is to call payments.sendPaymentForm, with the following parameters:
- The msg_id is set to the ID of the invoice message
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
The user enters their payment information as described above and presses the final pay button.
At this moment the Telegram API sends an updateBotPrecheckoutQuery constructor that contains all the available information about the order to the bot. 
The bot must reply using messages.setBotPrecheckoutResults within 10 seconds after receiving this update or the transaction is canceled.
The bot may return an error if it can't process the order for any reason. We highly recommend specifying a reason for failure to complete the order in human readable form (e.g. "Sorry, we're all out of rubber ducks! Would you be interested in a steel bear instead?"). Telegram will display this reason to the user.
### 5. Checkout
In case the bot confirms the order, Telegram requests the payment provider to complete the transaction. If the payment information was entered correctly and the payment goes through, the Telegram API will modify the invoice message and send a service message as described below. Once your bot receives this message, it should proceed with delivering the goods or services purchased by the user.
If all is OK, the user receives a payments.paymentResult in reply to the payments.sendPaymentForm query, containing info about the updated invoice message in the form of an updateEditMessage.
The invoice message will be updated as follows: the attached messageMediaInvoice will now have a receipt_msg_id field.
Clients should treat invoice messages with a receipt_msg_id field as receipt messages, locally modifying the label of the keyboardButtonBuy button to a localized version of the word Receipt.
From this point, clicking on the Receipt button should trigger a call to payments.getPaymentReceipt, providing the receipt_msg_id to the msg_id field, which will return info about the transaction.
The payment will also generate one service message of type messageActionPaymentSent or messageActionPaymentSentMe, replying to the invoice.
For bots, the service message will be of type messageActionPaymentSentMe, for users it will be a messageActionPaymentSent.
The recurring_init flag will be set if this payment also enables future recurring payments.
Further recurring payments will automatically send messageActionPaymentSentMe and messageActionPaymentSent messages with the recurring_used flag set.
