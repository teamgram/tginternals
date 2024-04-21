# auth.Authorization
Object contains info on user authorization.

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
auth.authorizationSignUpRequired#44747e9a flags:# terms_of_service:flags.0?help.TermsOfService = auth.Authorization;

---functions---

auth.signUp#80eee427 phone_number:string phone_code_hash:string first_name:string last_name:string = auth.Authorization;
auth.signIn#8d52a951 flags:# phone_number:string phone_code_hash:string phone_code:flags.0?string email_verification:flags.1?EmailVerification = auth.Authorization;
auth.importAuthorization#a57a7dad id:long bytes:bytes = auth.Authorization;
auth.importBotAuthorization#67a3ff2c flags:int api_id:int api_hash:string bot_auth_token:string = auth.Authorization;
auth.checkPassword#d18b4d16 password:InputCheckPasswordSRP = auth.Authorization;
auth.recoverPassword#37096c70 flags:# code:string new_settings:flags.0?account.PasswordInputSettings = auth.Authorization;
auth.importWebTokenAuthorization#2db873a9 api_id:int api_hash:string web_auth_token:string = auth.Authorization;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| auth.authorization | Contains user authorization info. |
| auth.authorizationSignUpRequired | An account with this phone number doesn't exist on telegram: the user has to enter basic information and sign up |


## Methods
| Method | Description |
| ---- | ----------- |
| auth.signUp | Registers a validated phone number in the system. |
| auth.signIn | Signs in a user with a validated phone number. |
| auth.importAuthorization | Logs in a user using a key transmitted from his native data-center. |
| auth.importBotAuthorization | Login as a bot |
| auth.checkPassword | Try logging to an account protected by a 2FA password. |
| auth.recoverPassword | Reset the 2FA password using the recovery code sent using auth.requestPasswordRecovery. |
| auth.importWebTokenAuthorization | Login by importing an authorization token |


