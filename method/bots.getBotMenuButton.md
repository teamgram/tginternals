# bots.getBotMenuButton
Gets the menu button action for a given user or for all users, previously set using bots.setBotMenuButton; users can see this information in the botInfo constructor.

```
botMenuButtonDefault#7533a588 = BotMenuButton;
botMenuButtonCommands#4258c205 = BotMenuButton;
botMenuButton#c7b57ce6 text:string url:string = BotMenuButton;
---functions---
bots.getBotMenuButton#9c60eb28 user_id:InputUser = BotMenuButton;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | User ID or empty for the default menu button. |


## Result
BotMenuButton

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | USER_BOT_REQUIRED | This method can only be called by a bot. |

