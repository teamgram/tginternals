# payments.getUniqueStarGift
Obtain info about a collectible gift » using a slug obtained from a collectible gift link ».

```
payments.uniqueStarGift#416c56e8 gift:StarGift chats:Vector<Chat> users:Vector<User> = payments.UniqueStarGift;
---functions---
payments.getUniqueStarGift#a1974d72 slug:string = payments.UniqueStarGift;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| slug | string | The slug. |


## Result
payments.UniqueStarGift

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STARGIFT_SLUG_INVALID | The specified gift slug is invalid. |

