# account.passwordSettings
Private info associated to the password info (recovery email, telegram passport info & so on)

```
account.passwordSettings#9a5c33e5 flags:# email:flags.0?string secure_settings:flags.1?SecureSecretSettings = account.PasswordSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| email | flags.0?string | 2FA Recovery email |
| secure_settings | flags.1?SecureSecretSettings | Telegram passport settings |


## Type
account.PasswordSettings

## Related pages
