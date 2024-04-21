# account.password
Configuration for two-factor authorization

```
account.password#957b50fb flags:# has_recovery:flags.0?true has_secure_values:flags.1?true has_password:flags.2?true current_algo:flags.2?PasswordKdfAlgo srp_B:flags.2?bytes srp_id:flags.2?long hint:flags.3?string email_unconfirmed_pattern:flags.4?string new_algo:PasswordKdfAlgo new_secure_algo:SecurePasswordKdfAlgo secure_random:bytes pending_reset_date:flags.5?int login_email_pattern:flags.6?string = account.Password;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| has_recovery | flags.0?true | Whether the user has a recovery method configured |
| has_secure_values | flags.1?true | Whether telegram passport is enabled |
| has_password | flags.2?true | Whether the user has a password |
| current_algo | flags.2?PasswordKdfAlgo | The KDF algorithm for SRP two-factor authentication of the current password |
| srp_B | flags.2?bytes | Srp B param for SRP authorization |
| srp_id | flags.2?long | Srp ID param for SRP authorization |
| hint | flags.3?string | Text hint for the password |
| email_unconfirmed_pattern | flags.4?string | A password recovery email with the specified pattern is still awaiting verification |
| new_algo | PasswordKdfAlgo | The KDF algorithm for SRP two-factor authentication to use when creating new passwords |
| new_secure_algo | SecurePasswordKdfAlgo | The KDF algorithm for telegram passport |
| secure_random | bytes | Secure random string |
| pending_reset_date | flags.5?int | The 2FA password will be automatically removed at this date, unless the user cancels the operation |
| login_email_pattern | flags.6?string | A verified login email with the specified pattern is configured |


## Type
account.Password

## Related pages
