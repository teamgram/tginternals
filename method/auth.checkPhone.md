# auth.checkPhone
Returns information on whether the passed phone number was registered.

```
Method schema is available as of layer 78. Switch »
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| phone_number | string | Phone number in the international format |


## Result
The method returns an auth.CheckedPhone type object with information on whether an account with such a phone number has already been registered, as well as whether invitations were sent to this number (using the auth.sendInvites method).

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | PHONE_NUMBER_BANNED | The provided phone number is banned from telegram |
| 400 | PHONE_NUMBER_INVALID | Invalid phone number |

