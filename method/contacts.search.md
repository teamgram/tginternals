# contacts.search
Returns users found by username substring.

```
contacts.found#b3134d9d my_results:Vector<Peer> results:Vector<Peer> chats:Vector<Chat> users:Vector<User> = contacts.Found;
---functions---
contacts.search#11f812d8 q:string limit:int = contacts.Found;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| q | string | Target substring |
| limit | int | Maximum number of users to be returned |


## Result
contacts.Found

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | QUERY_TOO_SHORT | The query string is too short. |
| 400 | SEARCH_QUERY_EMPTY | The search query is empty. |

