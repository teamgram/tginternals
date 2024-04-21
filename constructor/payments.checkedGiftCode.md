# payments.checkedGiftCode
Contains info about a Telegram Premium giftcode link.

```
payments.checkedGiftCode#284a1096 flags:# via_giveaway:flags.2?true from_id:flags.4?Peer giveaway_msg_id:flags.3?int to_id:flags.0?long date:int months:int used_date:flags.1?int chats:Vector<Chat> users:Vector<User> = payments.CheckedGiftCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| via_giveaway | flags.2?true | Whether this giftcode was created by a giveaway. |
| from_id | flags.4?Peer | The peer that created the gift code. |
| giveaway_msg_id | flags.3?int | Message ID of the giveaway in the channel specified in from_id. |
| to_id | flags.0?long | The destination user of the gift. |
| date | int | Creation date of the gift code. |
| months | int | Duration in months of the gifted Telegram Premium subscription. |
| used_date | flags.1?int | When was the giftcode imported, if it was imported. |
| chats | Vector<Chat> | Mentioned chats |
| users | Vector<User> | Mentioned users |


## Type
payments.CheckedGiftCode

## Related pages
