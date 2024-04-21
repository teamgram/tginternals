# bots.answerWebhookJSONQuery
Answers a custom query; for bots only

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
bots.answerWebhookJSONQuery#e6213f4d query_id:long data:DataJSON = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| query_id | long | Identifier of a custom query |
| data | DataJSON | JSON-serialized answer to the query |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | DATA_JSON_INVALID | The provided JSON data is invalid. |
| 400 | QUERY_ID_INVALID | The query ID is invalid. |
| 403 | USER_BOT_INVALID | User accounts must provide the bot method parameter when calling this method. If there is no such method parameter, this method can only be invoked by bot accounts. |

