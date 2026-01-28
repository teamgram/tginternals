# account.createBusinessChatLink
Create a business chat deep link ».

```
businessChatLink#b4ae666f flags:# link:string message:string entities:flags.0?Vector<MessageEntity> title:flags.1?string views:int = BusinessChatLink;
---functions---
account.createBusinessChatLink#8851e68e link:InputBusinessChatLink = BusinessChatLink;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| link | InputBusinessChatLink | Info about the link to create. |


## Result
BusinessChatLink

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHATLINKS_TOO_MUCH | Too many business chat links were created, please delete some older links. |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |

