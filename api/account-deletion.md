# Account deletion

A user can delete their Telegram account using account.deleteAccount.

If the account doesn't have a 2FA password, calling this method  will immediately delete the Telegram account.
If the account has a 2FA password and it is provided to account.deleteAccount:password, calling this method will immediately delete the Telegram account.

If the account has a 2FA password but the user doesn't remember it, password reset may be requested first », or otherwise, the password field may simply be left empty.

In this case, if the account's 2FA password was modified more than 7 days ago and was active in the last 7 days, account deletion will be delayed for 7 days.
Otherwise, the account will be immediately deleted.
In the first case, a service message will be sent to the user, containing a phone number confirmation link ».

When such a link is clicked, account.sendConfirmPhoneCode must be called with the specified hash, using the account with the specified phone number.
This will send a phone number verification code to the phone number associated with the account.
The phone code settings are the same as for the login code, and auth.cancelCode with auth.resendCode can be used as well, to resend or cancel the phone code as for the login code.

Once the SMS code is received, the account.confirmPhone method will have to be called with the SMS code and the phone hash received from the account.sendConfirmPhoneCode method.

This will cancel deletion of the account and will log out the user that tried to reset it.
Otherwise, if the number isn't confirmed in 7 days, the account will be deleted and the user will be free to recreate it.

### User Authorization

How to register a user's phone to start using the API.

### Two-factor authentication

How to login to a user's account if they have enabled 2FA, how to change password.

### Deep links

Telegram clients must handle special tg:// and t.me deep links encountered in messages, link entities and in other apps by registering OS handlers.

