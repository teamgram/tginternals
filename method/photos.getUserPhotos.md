# photos.getUserPhotos
Returns the list of user photos.

```
photos.photos#8dca6aa5 photos:Vector<Photo> users:Vector<User> = photos.Photos;
photos.photosSlice#15051f54 count:int photos:Vector<Photo> users:Vector<User> = photos.Photos;
---functions---
photos.getUserPhotos#91cd32a8 user_id:InputUser offset:int max_id:long limit:int = photos.Photos;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| user_id | InputUser | User ID |
| offset | int | Number of list elements to be skipped |
| max_id | long | If a positive value was transferred, the method will return only photos with IDs less than the set one. This parameter is often useful when refetching file references », as in conjuction with limit=1 and offset=-1 the photo object with the id specified in max_id can be fetched. |
| limit | int | Number of list elements to be returned |


## Result
photos.Photos

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | MAX_ID_INVALID | The provided max ID is invalid. |
| 400 | MSG_ID_INVALID | Invalid message ID provided. |
| 400 | USER_ID_INVALID | The provided user ID is invalid. |

