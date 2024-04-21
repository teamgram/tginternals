# account.getAuthorizationForm
Returns a Telegram Passport authorization form for sharing data with a service

```
account.authorizationForm#ad2e1cd8 flags:# required_types:Vector<SecureRequiredType> values:Vector<SecureValue> errors:Vector<SecureValueError> users:Vector<User> privacy_policy_url:flags.0?string = account.AuthorizationForm;
---functions---
account.getAuthorizationForm#a929597a bot_id:long scope:string public_key:string = account.AuthorizationForm;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot_id | long | User identifier of the service's bot |
| scope | string | Telegram Passport element types requested by the service |
| public_key | string | Service's public key |


## Result
account.AuthorizationForm

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PUBLIC_KEY_REQUIRED | A public key is required. |

