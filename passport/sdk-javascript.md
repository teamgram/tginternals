# Javascript SDK

The Javascript SDK helps you easily integrate Telegram Passport requests into your website. Check out our GitHub repository to see samples using this SDK.

### Installation

Download and include the Javascript SDK in the head section of your page:

```
<script src="telegram-passport.js"></script>
```

### Usage

Simply call Telegram.Passport.createAuthButton to create the default Telegram Passport button:

```
<div id="telegram_passport_auth"></div>
<script>
  Telegram.Passport.createAuthButton('telegram_passport_auth', {
    bot_id:       123456, // place id of your bot here
    scope:        {data: [{type: 'id_document', selfie: true}, 'address_document', 'phone_number', 'email'], v: 1},
    public_key:   '-----BEGIN PUBLIC KEY----- ...', // place public key of your bot here
    nonce:        'ab2df83746a87d2f3bd6...', // place nonce here
    callback_url: 'https://example.com/callback/' // place callback url here
  });
</script>
```

> Note that if you use a Content-Security-Policy (CSP) header with the frame-src/child-src directive you should allow tg: source to prevent errors in some browsers (e.g. Firefox)

#### createAuthButton

#### AuthParameters

#### AuthButtonOptions

You can also create your custom button. Do not forget about the tooltip. You should add an onclick listener to the button which calls the Telegram.Passport.auth(auth_params, tooltip_toggle); method:

```
<button id="telegram_passport_auth">Log In With Telegram</button>
<script>
  var auth_button = document.getElementById('telegram_passport_auth');
  var auth_params = {
    bot_id:        XXXXXX, // place id of your bot here
    scope:         {data: [{type: 'id_document', selfie: true}, 'address_document', 'phone_number', 'email'], v: 1},
    public_key:    '-----BEGIN PUBLIC KEY----- ...', // place public key of your bot here
    nonce:         'ab2df83746a87d2f3bd6...', // place nonce here
    callback_url:  'https://example.com/callback/' // place callback url here
  };
  auth_button.addEventListener('click', function() {
    Telegram.Passport.auth(auth_params, function(show) {
      if (show) {
        // some code to show tooltip
      } else {
        // some code to hide tooltip
      }
    });
  }, false);
</script>
```

### Receiving information

When the user confirms your request by pressing the "Authorize" button, it will be redirected to the URL specified in the callback_url with the parameter tg_passport=success and the Bot API will send the bot an Update with the field passport_data which contains encrypted Telegram Passport data.

If the user cancels your request, it will be redirected to the URL specified in the callback_url with the parameter tg_passport=cancel.

If an error occurs during the request, the user will be redirected to the URL specified in the callback_url with the parameter tg_passport=error. The parameter error will contain one of the following values: BOT_INVALID, PUBLIC_KEY_REQUIRED, PUBLIC_KEY_INVALID, SCOPE_EMPTY, NONCE_EMPTY.

