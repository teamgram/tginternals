# account.editBusinessChatLink
Edit a created business chat deep link ».

```
businessChatLink#b4ae666f flags:# link:string message:string entities:flags.0?Vector<MessageEntity> title:flags.1?string views:int = BusinessChatLink;
---functions---
account.editBusinessChatLink#8c3410af slug:string link:InputBusinessChatLink = BusinessChatLink;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| slug | string | Slug of the link, obtained as specified here ». |
| link | InputBusinessChatLink | New link information. |


## Result
BusinessChatLink

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHATLINK_SLUG_EMPTY | The specified slug is empty. |
| 403 | PREMIUM_ACCOUNT_REQUIRED | A premium account is required to execute this action. |

