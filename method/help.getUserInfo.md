# help.getUserInfo
Can only be used by TSF members to obtain internal information.

```
help.userInfoEmpty#f3ae2eed = help.UserInfo;
help.userInfo#1eb3758 message:string entities:Vector<MessageEntity> author:string date:int = help.UserInfo;
---functions---
help.getUserInfo#38a08d3 user_id:InputUser = help.UserInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | User ID |


## Result
help.UserInfo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | USER_INVALID | Invalid user provided. |

