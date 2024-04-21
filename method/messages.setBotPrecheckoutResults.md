# messages.setBotPrecheckoutResults
Once the user has confirmed their payment and shipping details, the bot receives an updateBotPrecheckoutQuery update.
Use this method to respond to such pre-checkout queries.
Note: Telegram must receive an answer within 10 seconds after the pre-checkout query was sent.

```
boolFalse#bc799737 = Bool;
boolTrue#997275b5 = Bool;
---functions---
messages.setBotPrecheckoutResults#9c2dd95 flags:# success:flags.1?true query_id:long error:flags.0?string = Bool;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| success | flags.1?true | Set this flag if everything is alright (goods are available, etc.) and the bot is ready to proceed with the order, otherwise do not set it, and set the error field, instead |
| query_id | long | Unique identifier for the query to be answered |
| error | flags.0?string | Required if the success isn't set. Error message in human readable form that explains the reason for failure to proceed with the checkout (e.g. "Sorry, somebody just bought the last of our amazing black T-shirts while you were busy filling out your payment details. Please choose a different color or garment!"). Telegram will display this message to the user. |


## Result
Bool

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | ERROR_TEXT_EMPTY | The provided error message is empty. |

