# account.getUniqueGiftChatThemes
Obtain all chat themes » associated to owned collectible gifts ».

```
account.chatThemesNotModified#e011e1c4 = account.ChatThemes;
account.chatThemes#16484857 flags:# hash:long themes:Vector<ChatTheme> chats:Vector<Chat> users:Vector<User> next_offset:flags.0?int = account.ChatThemes;
---functions---
account.getUniqueGiftChatThemes#fe74ef9f offset:int limit:int hash:long = account.ChatThemes;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| offset | int | Offset for pagination. |
| limit | int | Maximum number of results to return, see pagination |
| hash | long | Hash from a previously returned account.chatThemes constructor, to avoid returning any result if the theme list hasn't changed. |


## Result
account.ChatThemes

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

