# bots.updateUserEmojiStatus
Change the emoji status of a user (invoked by bots, see here » for more info on the full flow)

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.updateUserEmojiStatus#ed9f30c5 user_id:InputUser emoji_status:EmojiStatus = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | The user whose emoji status should be changed |
| emoji_status | EmojiStatus | The emoji status |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |
| 403 | USER_PERMISSION_DENIED | The user hasn't granted or has revoked the bot's access to change their emoji status using bots.toggleUserEmojiStatusPermission. |

