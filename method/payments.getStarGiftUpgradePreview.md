# payments.getStarGiftUpgradePreview
Obtain a preview of the possible attributes (chosen randomly) a gift » can receive after upgrading it to a collectible gift », see here » for more info.

```
payments.starGiftUpgradePreview#167bd90b sample_attributes:Vector<StarGiftAttribute> = payments.StarGiftUpgradePreview;
---functions---
payments.getStarGiftUpgradePreview#9c9abcb1 gift_id:long = payments.StarGiftUpgradePreview;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| gift_id | long | The gift to upgrade. |


## Result
payments.StarGiftUpgradePreview

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | STARGIFT_INVALID | The passed gift is invalid. |

