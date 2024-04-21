# authorization
Logged-in session

```
authorization#ad01d61d flags:# current:flags.0?true official_app:flags.1?true password_pending:flags.2?true encrypted_requests_disabled:flags.3?true call_requests_disabled:flags.4?true unconfirmed:flags.5?true hash:long device_model:string platform:string system_version:string api_id:int app_name:string app_version:string date_created:int date_active:int ip:string country:string region:string = Authorization;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| current | flags.0?true | Whether this is the current session |
| official_app | flags.1?true | Whether the session is from an official app |
| password_pending | flags.2?true | Whether the session is still waiting for a 2FA password |
| encrypted_requests_disabled | flags.3?true | Whether this session will accept encrypted chats |
| call_requests_disabled | flags.4?true | Whether this session will accept phone calls |
| unconfirmed | flags.5?true | Whether the session is unconfirmed, see here » for more info. |
| hash | long | Identifier |
| device_model | string | Device model |
| platform | string | Platform |
| system_version | string | System version |
| api_id | int | API ID |
| app_name | string | App name |
| app_version | string | App version |
| date_created | int | When was the session created |
| date_active | int | When was the session last active |
| ip | string | Last known IP |
| country | string | Country determined from IP |
| region | string | Region determined from IP |


## Type
Authorization

## Related pages
