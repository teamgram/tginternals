# auth.authorization
Contains user authorization info.

```
auth.authorization#2ea2c0d4 flags:# setup_password_required:flags.1?true otherwise_relogin_days:flags.1?int tmp_sessions:flags.0?int future_auth_token:flags.2?bytes user:User = auth.Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| setup_password_required | flags.1?true | Suggests the user to set up a 2-step verification password to be able to log in again |
| otherwise_relogin_days | flags.1?int | Iff setup_password_required is set and the user declines to set a 2-step verification password, they will be able to log into their account via SMS again only after this many days pass. |
| tmp_sessions | flags.0?int | Temporary passport sessions |
| future_auth_token | flags.2?bytes | A future auth token |
| user | User | Info on authorized user |


## Type
auth.Authorization

## Related pages
