# Mini Apps on Telegram

Interactive HTML5 Mini Apps on Telegram can completely replace any website.

They support seamless authorization, integrated payments via multiple payment providers (with Google Pay and Apple Pay out of the box), delivering tailored push notifications to users, and much more.

This article offers a client-side overview of the implementation of bot mini apps using the MTProto API: see here for an overview of the mini-app side JS API ».

### Outgoing events: Mini App to client

Mini Apps can send web events starting with web_app_; see the web event documentation for the full list of events that can be sent by the Mini App to the client ».

### Incoming events: Client to Mini App

Mini Apps can also receive events, by exposing a window.Telegram.WebView.receiveEvent("event_name", params) method.

Here's the full list of events that can be received by a Mini App from the client, if the client invokes the receiveEvent method.

#### main_button_pressed

Params: null

Sent by the client when the user presses the main button located at the bottom of the webview, handle this event only if the main button was previously configured by a web_app_setup_main_button event ».

#### back_button_pressed

Params: null

Sent by the client when the user presses the (OS or UI) back button, if it was previously enabled by a web_app_setup_back_button event ».

#### settings_button_pressed

Params: null

Sent by the client when the user presses the settings button, if it was previously enabled by a web_app_setup_settings_button event ».

#### invoice_closed

Params: JSON object with the following fields:

- slug - Invoice identifier (string)

- status - One of the following values (string):

- cancelled – The user closed the invoice popup without paying, before the call to payments.sendPaymentForm.

- failed – The user tried to pay, but the payment failed: the call to payments.sendPaymentForm returned an RPC error and the popup was closed.

- pending – The payment is still processing: the bot will receive a further service message about a successful payment. payments.sendPaymentForm was successfully invoked returning payments.paymentVerificationNeeded, the user completed all additional verification forms returned by the method and the invoice popup was closed, but the client hasn't received a messageActionPaymentSent service message yet.

- Note that eventual errors will not be sent as a failed event if the user fails additional validation (ie 3-D Secure) returned by payments.paymentVerificationNeeded: the state will remaing pending.

- paid – The invoice was paid successfully: the client completed the payment flow », the invoice popup was closed and a messageActionPaymentSent service message was received by the client.

Sent by the client to report the payment status of an invoice obtained from a web_app_open_invoice event ».

#### viewport_changed

Params: a JSON object with the following fields:

- height - The current height of the visible area of the Mini App (excluding the bottom main button, if visible) (integer)

- is_state_stable - If true, the viewport is currently being resized (animation in progress), more events of this type may be emitted. (boolean)

- is_expanded - Whether the Mini App is expanded to its maximum height after the user swiped up or after the Mini App emitted a web_app_expand event (boolean)

Emitted when the viewport is changed.

#### theme_changed

Params: a JSON object with the following fields:

- theme_params - A theme parameters object » (object)

Emitted when requested by the Mini App using a web_app_request_theme event », or when the app theme changes.

##### Theme parameters

Bot Mini Apps can be themed according to the following theme parameters, passed as a JSON object to the theme_params parameter of the messages.requestSimpleWebView, messages.requestWebView and messages.requestAppWebView methods.

This JSON object has the following keys, containing color theme information (hex string, RGB, no alpha) to pass to the Mini App:

- bg_color - Background color

- secondary_bg_color - Secondary background color

- text_color - Text color

- hint_color - Hint text color

- link_color - Link color

- button_color - Button color

- button_text_color - Button text color

- header_bg_color - Header background color

- accent_text_color - Accent text color

- section_bg_color - Section background color

- section_header_text_color - Section header text color

- subtitle_text_color - Sub title text color

- destructive_text_color - Text color for destructive action buttons in prompts

#### popup_closed

Params: a JSON object with an optional button_id string field.

Emitted when the user presses a button or cancels a popup brought up by a previous web_app_open_popup event ».

#### write_access_requested

Params: a JSON object with the following fields:

- status - allowed or cancelled

Used by clients to reply to a web_app_request_write_access event », indicating whether the user has allowed the bot to send messages to the user (allowed) or not (cancelled).

#### phone_requested

Params: a JSON object with the following fields:

- status - sent or cancelled

Used by clients to reply to a web_app_request_phone event », indicating whether the user has shared their phone number with the bot (allowed) or not (cancelled).

#### custom_method_invoked

Params: a JSON object with the following fields:

- req_id - The req_id from the web_app_invoke_custom_method request

- result - The JSON data contained in the response of the bots.invokeWebViewCustomMethod method, if the method call succeeded

- error - The text of the RPC error, if the method call failed

Used by clients to reply to web_app_invoke_custom_method events ».

#### clipboard_text_received

Params: a JSON object with the following fields:

- req_id - The req_id from the web_app_read_text_from_clipboard request

- data - A string with the clipboard contents (optional, if not provided consider the request failed)

Used by clients to reply to web_app_read_text_from_clipboard events ».

#### qr_text_received

Params: a JSON object with the following fields:

- data - string with the contents of a scanned QR code.

Emitted by clients if a new QR code was scanned by the native QR code scanner opened with a web_app_open_scan_qr_popup event ».

#### scan_qr_popup_closed

Params: null or an empty object

Emitted by clients if the QR code scanner popup opened with a web_app_open_scan_qr_popup event » was closed by the user or failed to open altogether due to permission issues.

### Keyboard Button Mini Apps

Schema:

Keyboard Button Mini Apps should be opened when the user clicks a keyboardButtonSimpleWebView contained in a reply keyboard identified by a replyKeyboardMarkup constructor, by invoking messages.requestSimpleWebView passing the button's url to the url parameter.

After invoking messages.requestSimpleWebView and obtaining a simpleWebViewResultUrl result, clients should open a webview using the url contained in the returned simpleWebViewResultUrl.

Keyboard Button Mini Apps can send data back to the bot through the MTProto API via a web_app_data_send JS event ».

Upon receiving a web_app_data_send JS event » only from Keyboard Button Mini Apps, clients should invoke messages.sendWebViewData, passing the following arguments:

- bot - Bot ID

- random_id - Unique random ID to avoid resending the same event multiple times

- button_text - Text of the keyboardButtonSimpleWebView that was pressed to open the simple Mini App

- data - Contents of the data field of the JS event.

Make sure to ignore all web_app_data_send events sent after the first one, messages.sendWebViewData must be called only once. The webview must be closed after invoking the messages.sendWebViewData method.

This will generate a messageActionWebViewDataSent update for the user, and a messageActionWebViewDataSentMe update for the bot, containing the event data.

### Inline button Mini Apps

Schema:

Inline Button Mini Apps work similarly to inline bots »: they send messages on behalf of the user to the chat from which the query originated.

When the user clicks on an keyboardButtonWebView inline button contained in an inline keyboard identified by a replyInlineMarkup constructor, messages.requestWebView should be invoked, passing keyboardButtonWebView.url must be passed to the method's url parameter.

Then, clients should open a webview using the url contained in the returned webViewResultUrl.

After loading the webview, until it is closed by a web_app_close event, the user client must invoke messages.prolongWebView every 60 seconds: if the method call returns QUERY_ID_INVALID, the webview must be closed.

The opened URL's fragment parameters already contain basic information about the user and a query_id parameter, that is exposed by the bot Mini Apps JS library: this query_id can then be passed to the bot (within the Mini App itself, for example via an AJAX query or form submission to the server hosting the Mini App and the bot) and then used by the bot to invoke messages.sendWebViewResultMessage, passing an InputBotInlineResult constructor that will automatically send a message with optionally attached media, and even inline buttons on behalf of the user.

### Menu button Mini Apps

Menu button Mini Apps work similarly to inline button Mini Apps »: they send messages on behalf of the user to the chat from where the bot menu button » was clicked.

Menu button Mini Apps can be opened from a botMenuButton menu button »: in this case, the messages.requestWebView.from_bot_menu flag should be set, and the botMenuButton.url field must be passed to the method's url parameter.

The full flow is identical to the flow for inline button Mini Apps », apart from the different flags passed to messages.requestWebView, as described above.

### Attachment menu Mini Apps

Attachment menu Mini Apps work similarly to inline button Mini Apps »: they send messages on behalf of the user to the chat where the bot's attachment menu » was opened.

Attachment menu Mini Apps can be opened from an attachment menu entry »: in this case, no special flag should be set when invoking messages.requestWebView.

Attachment menu Mini Apps can also be opened from a bot attachment menu deep link, in which case the start_parameter should be provided to messages.requestWebView.start_param, if present.

The full flow is identical to the flow for inline button Mini Apps », apart from the different flags passed to messages.requestWebView, as described above.

### Inline mode Mini Apps

Not to be confused with inline button mini apps ».

Inline mode Mini Apps can be used to generate a custom set of inline results in response to a user's inline query » via a web_app_switch_inline_query JS event ».

Inline mode Mini Apps can be opened by clicking on an inlineBotWebView button returned at the top of the inline result list, contained in messages.botResults.switch_webview, returned by messages.getInlineBotResults.

Pass the url to messages.requestSimpleWebView, while also setting the from_switch_webview flag.

After invoking messages.requestSimpleWebView and obtaining a simpleWebViewResultUrl result, clients should open a webview using the url contained in the returned simpleWebViewResultUrl.

Once the user has finished making their choices in the Mini App, a web_app_switch_inline_query JS event » should be emitted, containing a JSON object with the following fields:

- query - The inline query that will be inserted in the chat's input field, after the bot's username.

- May be an empty string, in which case just the bot's username will be inserted, triggering an empty inline query.

- chat_types - An array of strings, containing a combination of users, bots, groups, channels.

- If non-empty, the client should prompt the user to choose a specific chat of the specified type(s), then open the chosen chat and inserts the bot's username and the specified inline query in the input field.

- The array values specify which types of chats the user will be able to choose from.

- If empty, the current chat is used.

Upon receiving a web_app_switch_inline_query JS event » from the Mini App, the client should make a new inline query » to the same bot, with the newly specified query, either in the current chat or in the newly chosen chat, as specified by the chat_types field.

### Side menu Mini Apps

Side menu Mini Apps can be opened by clicking on the installed side menu entry ».

This action must trigger a messages.requestSimpleWebView query with the from_side_menu flag set: clients should open a webview using the url contained in the returned simpleWebViewResultUrl.

Side menu Mini Apps can also be opened by clicking on a Mini App link »: in which case the start_parameter should be provided to messages.requestSimpleWebView.start_param, if present; note that in this case, the app should be opened (with an installation prompt » before, if not already installed) even if the client is minimized.

After invoking messages.requestSimpleWebView and obtaining a simpleWebViewResultUrl result, clients should open a webview using the url contained in the returned simpleWebViewResultUrl.

### Direct Link Mini Apps

Schema:

Another way to open Mini Apps is by using Direct Mini App links ».

These links are different from all other Mini App links, because they don't require the user to install an attachment menu, and a single bot can offer multiple Mini Apps, distinguished by their short_name.

These links should be handled as follows:

- Check if bot_username parameter of the link is indeed a bot username, if so then

- Invoke messages.getBotApp, passing an inputBotAppShortName with the short_name contained in the appname query string parameter.

- If the client has already encountered an app with this short name from the same bot before, pass the hash of the cached botApp constructor to messages.getBotApp.

- If a messages.botApp constructor is returned, open the Mini App by invoking messages.requestAppWebView, generating an inputBotAppID constructor from id and access_hash of the returned botApp, or from previously cached information if we already met the bot app and botAppNotModified was returned.

- If the client has clicked on the link in a Telegram chat, pass the chat's peer information into peer; otherwise pass the bot's peer information, instead.

- If the messages.botApp.request_write_access flag is set, the bot is asking permission to send messages to the user: ask confirmation from the user with a prompt and a checkbox, and if the user agrees, set the write_allowed flag when invoking messages.requestAppWebView.

- If the messages.botApp.inactive flag is set, ask confirmation from the user before opening the Mini App; the request_write_access checkbox should be shown in this prompt, if needed.

- Confirmation should always be asked, even if the inactive flag is not set, when opening the link from places where the full link is not visible (i.e. messageEntityTextUrl text links, inline buttons etc.).

- Don't use two prompts if confirmation to open the Mini App is required and request_write_access is set, use just one prompt with an optional checkbox for request_write_access.

- If the startapp query string parameter is present, pass it to start_param when invoking messages.requestAppWebView.

Finally, open the webview using the url contained in the returned appWebViewResultUrl.

