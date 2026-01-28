# account.deleteBusinessChatLink
Delete a business chat deep link ».

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
account.deleteBusinessChatLink#60073674 slug:string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| slug | string | Slug of the link, obtained as specified here ». |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | CHATLINK_SLUG_EMPTY | The specified slug is empty. |
| 400 | CHATLINK_SLUG_EXPIRED | The specified business chat link has expired. |

