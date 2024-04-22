# Account.AuthorizationForm
Authorization form

```
account.authorizationForm#ad2e1cd8 flags:# required_types:Vector<SecureRequiredType> values:Vector<SecureValue> errors:Vector<SecureValueError> users:Vector<User> privacy_policy_url:flags.0?string = account.AuthorizationForm;

---functions---

account.getAuthorizationForm#a929597a bot_id:long scope:string public_key:string = account.AuthorizationForm;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| account.authorizationForm | Telegram Passport authorization form |


## Methods
| Method | Description |
| ---- | ----------- |
| account.getAuthorizationForm | Returns a Telegram Passport authorization form for sharing data with a service |


