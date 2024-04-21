# updateBotShippingQuery
This object contains information about an incoming shipping query.

```
updateBotShippingQuery#b5aefd7d query_id:long user_id:long payload:bytes shipping_address:PostAddress = Update;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| query_id | long | Unique query identifier |
| user_id | long | User who sent the query |
| payload | bytes | Bot specified invoice payload |
| shipping_address | PostAddress | User specified shipping address |


## Type
Update

## Related pages
