# help.editUserInfo
Internal use

```
help.userInfoEmpty#f3ae2eed = help.UserInfo;
help.userInfo#1eb3758 message:string entities:Vector<MessageEntity> author:string date:int = help.UserInfo;
---functions---
help.editUserInfo#66b91b70 user_id:InputUser message:string entities:Vector<MessageEntity> = help.UserInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | User |
| message | string | Message |
| entities | Vector<MessageEntity> | Message entities for styled text |


## Result
help.UserInfo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ENTITY_BOUNDS_INVALID | A specified entity offset or length is invalid, see here » for info on how to properly compute the entity offset/length. |
| 403 | USER_INVALID | Invalid user provided. |

