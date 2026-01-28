# bots.getBotRecommendations
Obtain a list of similarly themed bots, selected based on similarities in their subscriber bases, see here » for more info.

```
users.users#62d706b8 users:Vector<User> = users.Users;
users.usersSlice#315a4974 count:int users:Vector<User> = users.Users;
---functions---
bots.getBotRecommendations#a1b70815 bot:InputUser = users.Users;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | The method will return bots related to the passed bot. |


## Result
users.Users

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

