# Login via QR code

QR code login flow.

Related TL schema:

### Exporting a login token

First of all, auth.exportLoginToken must be called by the app that wants to log in to an existing Telegram account.
The method will return an auth.loginToken constructor, containing a binary login token and an expiration date (usually 30 seconds).

The login token must be encoded using base64url, embedded in a tg://login?token=base64encodedtoken URL and shown in the form of a QR code to the user.
After the expiration of the current QR code, the auth.exportLoginToken method must be recalled and a new QR code must be generated automatically.

### Accepting a login token

In order to log in, the QR code must be scanned and accepted by an already logged-in Telegram app using auth.acceptLoginToken.
The token must be extracted from the tg://login URI and base64url-decoded before using it in the method.

Possible errors returned by the method are:

- 400 - AUTH_TOKEN_INVALID, an invalid authorization token was provided

- 400 - AUTH_TOKEN_EXPIRED, the provided authorization token has expired and the updated QR-code must be re-scanned

- 400 - AUTH_TOKEN_ALREADY_ACCEPTED, the authorization token was already used

The method will return an authorization object, containing info about the app and session that we just authorized.

### Confirming (importing) the login token

After the logged-in app calls auth.acceptLoginToken and accepts the login token, the app that is trying to login will receive an updateLoginToken update, which should trigger a second call to the auth.exportLoginToken method.

This second call should then return an auth.loginTokenSuccess constructor, indicating successful login, essentially allowing further authorized interaction with the API.

If, however, there is a DC mismatch between the two apps, auth.loginTokenMigrateTo is returned instead, to which the app that is trying to login should respond by calling auth.importLoginToken with the specified token, to the specified DC.

This call should then finally return a auth.loginTokenSuccess constructor.

