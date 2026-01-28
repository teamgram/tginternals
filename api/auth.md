# User Authorization

Authorization is associated with a client's encryption key identifier: auth_key_id. No additional parameters need to be passed into methods following authorization.

To log in as a bot, follow these instructions ».

An alternative QR code-based login flow is also available ».

### Sending a verification code

Example implementations: telegram for android, tdlib.

To show a nicely formatted and validated phone number field, the help.countriesList constructor can be obtained using the help.getCountriesList method.The help.countriesList config and other configuration values are then used as described here ».

Then, a text message containing an authorization code is sent to the user's phone using auth.sendCode.However, this is not always the case, if future auth tokens are used:

#### Future auth tokens

When invoking auth.logOut on a previously authorized session, the server may return a future_auth_token, which should be stored in the local database.A future_auth_token is also contained in the auth.authorization returned when logging in.At all times, the future auth token database should contain at most 20 tokens: evict older tokens as new tokens are added to stay below this limit.When invoking auth.sendCode, all future auth tokens present in the database should be provided to codeSettings.logout_tokens.If any of the future auth tokens matches the account we're trying to login into and the token hasn't expired:

- If 2FA is not enabled, auth.sendCode will is directly return an auth.sentCodeSuccess constructor with session info, indicating the session is authorized.

- If 2FA is enabled, auth.sendCode will return a SESSION_PASSWORD_NEEDED RPC error, asking the user to enter the 2FA password, without sending any authorization code.

Otherwise, the system will send an authorization code using the following logic:

#### Code types

```
codeSettings#ad253d78 flags:# allow_flashcall:flags.0?true current_number:flags.1?true allow_app_hash:flags.4?true allow_missed_call:flags.5?true allow_firebase:flags.7?true unknown_number:flags.9?true logout_tokens:flags.6?Vector<bytes> token:flags.8?string app_sandbox:flags.8?Bool = CodeSettings;

auth.sentCodeTypeApp#3dbb5986 length:int = auth.SentCodeType;
auth.sentCodeTypeSms#c000bba2 length:int = auth.SentCodeType;
auth.sentCodeTypeCall#5353e5a7 length:int = auth.SentCodeType;
auth.sentCodeTypeFlashCall#ab03c6d9 pattern:string = auth.SentCodeType;
auth.sentCodeTypeMissedCall#82006484 prefix:string length:int = auth.SentCodeType;
auth.sentCodeTypeEmailCode#f450f59b flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true email_pattern:string length:int reset_available_period:flags.3?int reset_pending_date:flags.4?int = auth.SentCodeType;
auth.sentCodeTypeSetUpEmailRequired#a5491dea flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true = auth.SentCodeType;
auth.sentCodeTypeFragmentSms#d9565c39 url:string length:int = auth.SentCodeType;
auth.sentCodeTypeFirebaseSms#9fd736 flags:# nonce:flags.0?bytes play_integrity_project_id:flags.2?long play_integrity_nonce:flags.2?bytes receipt:flags.1?string push_timeout:flags.1?int length:int = auth.SentCodeType;
auth.sentCodeTypeSmsWord#a416ac81 flags:# beginning:flags.0?string = auth.SentCodeType;
auth.sentCodeTypeSmsPhrase#b37794af flags:# beginning:flags.0?string = auth.SentCodeType;

auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;
auth.sentCodePaymentRequired#d7a2fcf9 store_product:string phone_code_hash:string support_email_address:string support_email_subject:string = auth.SentCode;

---functions---

auth.sendCode#a677244f phone_number:string api_id:int api_hash:string settings:CodeSettings = auth.SentCode;
auth.resendCode#cae47523 flags:# phone_number:string phone_code_hash:string reason:flags.0?string = auth.SentCode;

auth.requestFirebaseSms#8e39261e flags:# phone_number:string phone_code_hash:string safety_net_token:flags.0?string play_integrity_token:flags.2?string ios_push_secret:flags.1?string = Bool;
```

The auth.sendCode method has parameters for enabling/disabling use of flash calls and missed calls, and allows passing an SMS token that will be included in the sent SMS.For example, the latter is required in newer versions of android, to use the android SMS receiver APIs.

The returned auth.sentCode object will contain multiple parameters:

The system will automatically choose how to send the authorization code; there are multiple possible ways the code can arrive, signaled to the client via the type field of the auth.SentCodeType constructor.

Note that in some conditions when signing up or logging in using an SMS code/call, only the auth.sentCodeTypeFirebaseSms code type may be used.

Currently, only mobile official apps can make use of Firebase SMS authentication: this means that in some conditions, only the official applications can receive a login/signup code via SMS/call.

Third-party apps and non-mobile official apps may log in using any of the other code delivery methods (Telegram codes, Fragment codes, email codes, future auth tokens, QR codes).

> Developers whose third-party apps require SMS authorization can contact us at sms@telegram.org, specifying #enableSMS in the email subject.

- auth.sentCodeTypeSetUpEmailRequired: if the user logins often enough, Telegram will ask the user to verify an email that will be used to send the login code.See here » for more info on the verification process.

- auth.sentCodeTypeEmailCode: the code was sent to the configured login email.

- auth.sentCodeTypeFragmentSms: the code was sent via fragment.com: open the specified url to log into the Fragment platform with your wallet and view the code.

- auth.sentCodeTypeApp: the code was sent as a Telegram service notification to all other logged-in sessions.

- auth.sentCodeTypeFirebaseSms: firebase login flow, only for official apps.

- On Android, can only be received if the codeSettings.allow_firebase flag is set.The client must pass the received auth.sentCodeTypeFirebaseSms.nonce/play_integrity_nonce to the SafetyNet Attestation API/Google Play Integrity API, and then pass the obtained JWS object to auth.requestFirebaseSms.safety_net_token/play_integrity_token, along with the phone_number and the phone_code_hash.If the method returns boolTrue, the code will be sent via SMS; otherwise, the next_type authentication method must be used, with auth.resendCode.The next_type authentication method must also be used if the device integrity verification failed, and no token could be obtained to invoke auth.requestFirebaseSms: in this case, the device integrity verification failure reason must be passed to auth.resendCode in reason.

- On iOS, can only be received if the device token for Apple Push was passed to codeSettings.token.The client then waits for a new push notification for auth.sentCodeTypeFirebaseSms.push_timeout seconds.If a push notification isn't received within push_timeout seconds, the next_type authentication method must be used, with auth.resendCode.If a push notification is received with receipt and ios_push_secret fields, and the value of the receipt field matches codeSettings.receipt, the value of ios_push_secret is passed to auth.requestFirebaseSms.ios_push_secret, along with the phone_number and the phone_code_hash.If the method returns boolTrue, the code will be sent via SMS; otherwise, the next_type authentication method must be used, with auth.resendCode.The next_type authentication method must also be used if the device integrity verification failed, and no secret could be obtained to invoke auth.requestFirebaseSms: in this case, the device integrity verification failure reason must be passed to auth.resendCode in reason.

- auth.sentCodeTypeSms: the code was sent via SMS.

- auth.sentCodeTypeSmsWord: the code was sent via SMS containing a single word, which is the SMS code to use.The beginning flag, if set, contains the first letter of the secret word.

- auth.sentCodeTypeSmsPhrase: the code was sent via SMS containing a phrase with multiple words, which are the SMS code to use.The beginning flag, if set, contains the first word of the secret phrase.

- auth.sentCodeTypeCall: the user will receive a phone call and a synthesized voice will tell the user the verification code to input.

- auth.sentCodeTypeFlashCall: the code will be sent via a flash phone call, that will be closed immediately.In this case, the phone code will then be the phone number itself, just make sure that the phone number matches the specified pattern (see auth.sentCodeTypeFlashCall).

- auth.sentCodeTypeMissedCall: the code will be sent via a flash phone call, that will be closed immediately.The last digits of the phone number that calls are the code that must be entered manually by the user.

- Future auth tokens »

If the message takes too long (timeout seconds) to arrive at the phone, the auth.resendCode method may be invoked to resend a code of type next_type.If the same happens again, you can use auth.resendCode with the next_type returned by the previous call to auth.resendCode.To cancel the verification code use auth.cancelCode.

Official apps may receive an auth.sentCodePaymentRequired instead: this constructor indicates that due to the high cost of SMS verification codes for the user's country/provider, the user must purchase a Telegram Premium subscription in order to proceed with the login/signup.

After a successful purchase of the specified store item, an updateSentPhoneCode update will be emitted, containing info about the sent code.

### Email verification

```
auth.sentCodeTypeSetUpEmailRequired#a5491dea flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true = auth.SentCodeType;

emailVerifyPurposeLoginSetup#4345be73 phone_number:string phone_code_hash:string = EmailVerifyPurpose;

emailVerificationCode#922e55a9 code:string = EmailVerification;
emailVerificationGoogle#db909ec2 token:string = EmailVerification;
emailVerificationApple#96d074fd token:string = EmailVerification;

account.sentEmailCode#811f854f email_pattern:string length:int = account.SentEmailCode;

account.emailVerifiedLogin#e1bb0d61 email:string sent_code:auth.SentCode = account.EmailVerified;

emailVerifyPurposeLoginChange#527d22eb = EmailVerifyPurpose;
account.emailVerified#2b96cd1b email:string = account.EmailVerified;

---functions---

account.sendVerifyEmailCode#98e037bb purpose:EmailVerifyPurpose email:string = account.SentEmailCode;
account.verifyEmail#32da4cf purpose:EmailVerifyPurpose verification:EmailVerification = account.EmailVerified;
auth.resetLoginEmail#7e960193 phone_number:string phone_code_hash:string = auth.SentCode;
```

Telegram may return a auth.sentCodeTypeSetUpEmailRequired code type in the auth.sentCode constructor returned by auth.sendCode.In this case, clients should ask the user to verify an email address that will be used to receive the login code as follows:

- If the google_signin_allowed or apple_signin_allowed flags are set, users can directly verify their email with Google/Apple ID as specified here (Google ID) » and here (Apple ID) ».After obtaining the ID token, call account.verifyEmail, providing the following parameters:

- purpose - A emailVerifyPurposeLoginSetup constructor

- purpose.phone_number - The phone number used with auth.sendCode

- purpose.phone_code_hash - The phone code hash contained in the auth.sentCode constructor returned by auth.sendCode

- verification - emailVerificationGoogle or emailVerificationApple

- verification.token - The ID token returned by the Google ID API.

- On success, the account.verifyEmail method will return a account.emailVerifiedLogin constructor with an auth.sentCode constructor that should be handled as usual ».

- Otherwise, ask the user to enter an email address and then call account.sendVerifyEmailCode, providing the following parameters:

- email - The email address

- purpose - A emailVerifyPurposeLoginSetup constructor

- purpose.phone_number - The phone number used with auth.sendCode

- purpose.phone_code_hash - The phone code hash contained in the auth.sentCode constructor returned by auth.sendCode

- Once the user receives and inputs the verification code, call account.verifyEmail, providing the following parameters:

- purpose - A emailVerifyPurposeLoginSetup constructor

- purpose.phone_number - The phone number used with auth.sendCode

- purpose.phone_code_hash - The phone code hash contained in the auth.sentCode constructor returned by auth.sendCode

- verification - emailVerificationCode

- verification.code - The verification code received by the user.

- On success, the account.verifyEmail method will return a account.emailVerifiedLogin constructor with an auth.sentCode constructor that should be handled as usual ».

If the user cannot access their email address, an email reset may be requested using auth.resetLoginEmail.

To change the login email after login, pass emailVerifyPurposeLoginChange as purpose, following the exact same Google ID/Apple ID/email code login flow as above: on success, the account.verifyEmail method will return an account.emailVerified constructor.

### Sign in/sign up

When user enters verification code, the auth.signIn method must be used to validate it and possibly sign user in.

If the code was entered correctly, but the method returns auth.authorizationSignUpRequired, it means that account with this phone number doesn't exist yet: user needs to provide basic information, accept terms of service and then the new user registration method (auth.signUp) must be invoked.

### 2FA

When trying to sign in using auth.signIn, an error 400 SESSION_PASSWORD_NEEDED may be returned, if the user has two-factor authentication enabled.In this case, instructions for SRP 2FA authentication must be followed.

To set up two-factor authorization on an already authorized account, follow the SRP 2FA authentication docs.

### Confirming login

```
authorization#ad01d61d flags:# current:flags.0?true official_app:flags.1?true password_pending:flags.2?true encrypted_requests_disabled:flags.3?true call_requests_disabled:flags.4?true unconfirmed:flags.5?true hash:long device_model:string platform:string system_version:string api_id:int app_name:string app_version:string date_created:int date_active:int ip:string country:string region:string = Authorization;

account.authorizations#4bff8ea0 authorization_ttl_days:int authorizations:Vector<Authorization> = account.Authorizations;

updateNewAuthorization#8951abef flags:# unconfirmed:flags.0?true hash:long date:flags.0?int device:flags.0?string location:flags.0?string = Update;

---functions---

account.getAuthorizations#e320c158 = account.Authorizations;

account.changeAuthorizationSettings#40f48462 flags:# confirmed:flags.3?true hash:long encrypted_requests_disabled:flags.0?Bool call_requests_disabled:flags.1?Bool = Bool;

account.resetAuthorization#df77f3bc hash:long = Bool;
```

When logging in, other logged-in sessions will receive an updateNewAuthorization update.If the unconfirmed flag is set, clients should display a notification, asking the user if they recognize the session.

If the user clicks on the Yes button, invoke account.changeAuthorizationSettings with the new session's hash and the confirmed flag set, confirming the specified session.

If the user clicks on the No button, invoke account.resetAuthorization with the new session's hash, logging out the specified session.

If no action is taken by the user, the session will be autoconfirmed authorization_autoconfirm_period seconds after login (see the associated client configuration parameter »).

### Invalidating login codes

Telegram's servers will automatically invalidate login codes if they are sent by the user to another Telegram chat, either by forwarding them or by sending them inside of a message: however, clients should also manually and immediately invalidate login codes if the user attempts to screenshot or forward a message sent by the login notification service user (ID 777000) containing login codes.

If an incoming message that is:

- Sent by the login notification service user (ID 777000)

- AND is a text message (not a media)

- AND contains one or more login codes, defined as a sequence of 5 to 7 decimal digits, optionally interleaved with or followed by any number of - characters (example implementation »)

Is either:

- Screenshotted by the user

- OR forwarded by the user to any chat

account.invalidateSignInCodes should be invoked, passing the extracted login codes (excluding any - characters).

```
---functions---

account.invalidateSignInCodes#ca8ae8ba codes:Vector<string> = Bool;
```

### Test Accounts

Each phone number is limited to only a certain amount of logins per day (e.g. 5, but this is subject to change) after which the API will return a FLOOD error until the next day. This might not be enough for testing the implementation of User Authorization flows in client applications.

There are several reserved phone number prefixes for testing that your application handles redirects between DCs, sign up, sign in and 2FA flows correctly. These numbers are only available on Test DCs (their IP addresses for TCP transport are available in API development tools panel after api_id was obtained, URI format for HTTPS/WebSocket transport).

If you wish to emulate an application of a user associated with DC number X, it is sufficient to specify the phone number as 99966XYYYY, where YYYY are random numbers, when registering the user. A user like this would always get XXXXX as the login confirmation code (the DC number, repeated five times). Note that the value of X must be in the range of 1-3 because there are only 3 Test DCs. When the flood limit is reached for any particular test number, just choose another number (changing the YYYY random part).

Do not store any important or private information in the messages of such test accounts; anyone can make use of the simplified authorization mechanism – and we periodically wipe all information stored there.

Proceed with User Authorization flows in Production DCs only after you make sure everything works correctly on Test DCs first to avoid reaching flood limits.

> To help you with working on production DCs, logins with the same phone number with which the api_id was registered have more generous flood limits.

### We are authorized

As a result of authorization, the client key, auth_key_id, becomes associated with the user, and each subsequent API call with this key will be executed with that user's identity. The authorization method itself returns the relevant user. It is best to immediately store the User ID locally in a binding with the key.

Only a small portion of the API methods are available to unauthorized users:

- account.deleteAccount

- account.getPassword

- account.sendVerifyEmailCode

- account.verifyEmail

- auth.bindTempAuthKey

- auth.cancelCode

- auth.checkPassword

- auth.exportLoginToken

- auth.importAuthorization

- auth.importBotAuthorization

- auth.importLoginToken

- auth.importWebTokenAuthorization

- auth.reportMissingCode

- auth.requestFirebaseSms

- auth.resendCode

- auth.resetLoginEmail

- auth.sendCode

- auth.signIn

- auth.signUp

- help.getAppConfig

- help.getConfig

- help.getCountriesList

- help.getDeepLinkInfo

- help.getNearestDc

- help.saveAppLog

- initConnection

- invokeWithLayer

- langpack.getDifference

- langpack.getLangPack

- langpack.getLanguage

- langpack.getLanguages

- langpack.getStrings

- payments.assignAppStoreTransaction

- payments.assignPlayMarketTransaction

- payments.canPurchaseStore

- payments.getPaymentForm

- payments.sendPaymentForm

Other methods will result in an error: 401 UNAUTHORIZED.

Note that a JSON version of the full list of methods that can be invoked over an unauthed connection is also available in the RPC db ».

### Frozen accounts

Accounts can be frozen for serious violations of Telegram's ToS.

Frozen accounts are in read-only mode, and invoking many methods will emit one of the following errors:

- FROZEN_METHOD_INVALID (420): the specified method cannot be used at all by frozen accounts.

- FROZEN_PARTICIPANT_MISSING (400): even if the specified method can be used by frozen accounts, the specified peer cannot be accessed by frozen accounts.

Frozen accounts are deleted after a specific amount of time, unless an appeal is submitted and accepted.

When receiving a FROZEN_METHOD_INVALID, clients should invoke help.getAppConfig to obtain the following newly populated fields:

- freeze_since_date - If set and non-zero, indicates when was the account frozen (integer, unixtime)

- freeze_until_date - If set and non-zero, indicates when will the account be deleted, unless an appeal is submitted and accepted to the freeze_appeal_url (integer, unixtime)

- freeze_appeal_url - A URL that the user can open to submit an appeal (string)

