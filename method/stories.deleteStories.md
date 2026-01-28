# stories.deleteStories
Deletes some posted stories.

```
---functions---
stories.deleteStories#ae59db5f peer:InputPeer id:Vector<int> = Vector<int>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | Channel/user from where to delete stories. |
| id | Vector<int> | IDs of stories to delete. |


## Result
Vector<int>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 403 | BOT_ACCESS_FORBIDDEN | The specified method can be used over a business connection for some operations, but the specified query attempted an operation that is not allowed over a business connection. |
| 400 | BUSINESS_CONNECTION_INVALID | The connection_id passed to the wrapping invokeWithBusinessConnection call is invalid. |
| 400 | CHANNEL_INVALID | The provided channel is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORY_ID_EMPTY | You specified no story IDs. |

