# users.setSecureValueErrors
Notify the user that the sent passport data contains some errors The user will not be able to re-submit their Passport data to you until the errors are fixed (the contents of the field for which you returned the error must change).

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
users.setSecureValueErrors#90c894b5 id:InputUser errors:Vector<SecureValueError> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| id | InputUser | The user |
| errors | Vector<SecureValueError> | Errors |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DATA_HASH_SIZE_INVALID | The size of the specified secureValueErrorData.data_hash is invalid. |
| 400 | HASH_SIZE_INVALID | The size of the specified secureValueError.hash is invalid. |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

