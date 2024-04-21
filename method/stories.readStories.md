# stories.readStories
Mark all stories up to a certain ID as read, for a given peer; will emit an updateReadStories update to all logged-in sessions.

```
---functions---
stories.readStories#a556dac8 peer:InputPeer max_id:int = Vector<int>;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| peer | InputPeer | The peer whose stories should be marked as read. |
| max_id | int | Mark all stories up to and including this ID as read |


## Result
Vector<int>

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MAX_ID_INVALID | The provided max ID is invalid. |
| 400 | PEER_ID_INVALID | The provided peer id is invalid. |
| 400 | STORIES_NEVER_CREATED | This peer hasn't ever posted any stories. |

