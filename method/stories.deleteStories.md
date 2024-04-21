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
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |

