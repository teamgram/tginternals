# bots.setBotMenuButton
Sets the menu button action » for a given user or for all users

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.setBotMenuButton#4504d54f user_id:InputUser button:BotMenuButton = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | User ID |
| button | BotMenuButton | Bot menu button action |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BUTTON_TEXT_INVALID | The specified button text is invalid. |
| 400 | BUTTON_URL_INVALID | Button URL invalid. |

