# account.passwordInputSettings
Settings for setting up a new password

```
account.passwordInputSettings#c23727c9 flags:# new_algo:flags.0?PasswordKdfAlgo new_password_hash:flags.0?bytes hint:flags.0?string email:flags.1?string new_secure_settings:flags.2?SecureSecretSettings = account.PasswordInputSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| new_algo | flags.0?PasswordKdfAlgo | The SRP algorithm to use |
| new_password_hash | flags.0?bytes | The computed password hash |
| hint | flags.0?string | Text hint for the password |
| email | flags.1?string | Password recovery email |
| new_secure_settings | flags.2?SecureSecretSettings | Telegram passport settings |


## Type
account.PasswordInputSettings

## Related pages
