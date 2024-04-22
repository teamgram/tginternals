# Javascript SDK

The Javascript SDK helps you easily integrate Telegram Passport requests into your website. Check out our GitHub repository to see samples using this SDK.

### Installation

Download and include the Javascript SDK in the head section of your page:

### Usage

Simply call Telegram.Passport.createAuthButton to create the default Telegram Passport button:

> Note that if you use a Content-Security-Policy (CSP) header with the frame-src/child-src directive you should allow tg: source to prevent errors in some browsers (e.g. Firefox)

#### createAuthButton

#### AuthParameters

#### AuthButtonOptions

You can also create your custom button. Do not forget about the tooltip. You should add an onclick listener to the button which calls the Telegram.Passport.auth(auth_params, tooltip_toggle); method:

### Receiving information

When the user confirms your request by pressing the "Authorize" button, it will be redirected to the URL specified in the callback_url with the parameter tg_passport=success and the Bot API will send the bot an Update with the field passport_data which contains encrypted Telegram Passport data.

If the user cancels your request, it will be redirected to the URL specified in the callback_url with the parameter tg_passport=cancel.

If an error occurs during the request, the user will be redirected to the URL specified in the callback_url with the parameter tg_passport=error. The parameter error will contain one of the following values: BOT_INVALID, PUBLIC_KEY_REQUIRED, PUBLIC_KEY_INVALID, SCOPE_EMPTY, NONCE_EMPTY.

