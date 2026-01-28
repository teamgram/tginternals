# fragment.getCollectibleInfo
Fetch information about a fragment collectible, see here » for more info on the full flow.

```
fragment.collectibleInfo#6ebdff91 purchase_date:int currency:string amount:long crypto_currency:string crypto_amount:long url:string = fragment.CollectibleInfo;
---functions---
fragment.getCollectibleInfo#be1e85ba collectible:InputCollectible = fragment.CollectibleInfo;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| collectible | InputCollectible | Collectible to fetch info about. |


## Result
fragment.CollectibleInfo

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | COLLECTIBLE_INVALID | The specified collectible is invalid. |
| 400 | COLLECTIBLE_NOT_FOUND | The specified collectible could not be found. |

