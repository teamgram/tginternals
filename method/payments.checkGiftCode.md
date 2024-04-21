# payments.checkGiftCode
Obtain information about a Telegram Premium giftcode »

```
payments.checkedGiftCode#284a1096 flags:# via_giveaway:flags.2?true from_id:flags.4?Peer giveaway_msg_id:flags.3?int to_id:flags.0?long date:int months:int used_date:flags.1?int chats:Vector<Chat> users:Vector<User> = payments.CheckedGiftCode;
---functions---
payments.checkGiftCode#8e51b4c1 slug:string = payments.CheckedGiftCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| slug | string | The giftcode to check |


## Result
payments.CheckedGiftCode

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | GIFT_SLUG_INVALID | The specified slug is invalid. |

