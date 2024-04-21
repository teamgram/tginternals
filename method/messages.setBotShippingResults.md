# messages.setBotShippingResults
If you sent an invoice requesting a shipping address and the parameter is_flexible was specified, the bot will receive an updateBotShippingQuery update. Use this method to reply to shipping queries.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setBotShippingResults#e5f672fa flags:# query_id:long error:flags.0?string shipping_options:flags.1?Vector<ShippingOption> = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| query_id | long | Unique identifier for the query to be answered |
| error | flags.0?string | Error message in human readable form that explains why it is impossible to complete the order (e.g. "Sorry, delivery to your desired address is unavailable"). Telegram will display this message to the user. |
| shipping_options | flags.1?Vector<ShippingOption> | A vector of available shipping options. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | QUERY_ID_INVALID | The query ID is invalid. |

