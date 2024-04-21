# account.authorizationForm
Telegram Passport authorization form

```
account.authorizationForm#ad2e1cd8 flags:# required_types:Vector<SecureRequiredType> values:Vector<SecureValue> errors:Vector<SecureValueError> users:Vector<User> privacy_policy_url:flags.0?string = account.AuthorizationForm;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| required_types | Vector<SecureRequiredType> | Required Telegram Passport documents |
| values | Vector<SecureValue> | Already submitted Telegram Passport documents |
| errors | Vector<SecureValueError> | Telegram Passport errors |
| users | Vector<User> | Info about the bot to which the form will be submitted |
| privacy_policy_url | flags.0?string | URL of the service's privacy policy |


## Type
account.AuthorizationForm

## Related pages
