# starsTransaction
Represents a Telegram Stars or TON transaction ».

```
starsTransaction#13659eb0 flags:# refund:flags.3?true pending:flags.4?true failed:flags.6?true gift:flags.10?true reaction:flags.11?true stargift_upgrade:flags.18?true business_transfer:flags.21?true stargift_resale:flags.22?true posts_search:flags.24?true stargift_prepaid_upgrade:flags.25?true id:string amount:StarsAmount date:int peer:StarsTransactionPeer title:flags.0?string description:flags.1?string photo:flags.2?WebDocument transaction_date:flags.5?int transaction_url:flags.5?string bot_payload:flags.7?bytes msg_id:flags.8?int extended_media:flags.9?Vector<MessageMedia> subscription_period:flags.12?int giveaway_post_id:flags.13?int stargift:flags.14?StarGift floodskip_number:flags.15?int starref_commission_permille:flags.16?int starref_peer:flags.17?Peer starref_amount:flags.17?StarsAmount paid_messages:flags.19?int premium_gift_months:flags.20?int ads_proceeds_from_date:flags.23?int ads_proceeds_to_date:flags.23?int = StarsTransaction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| refund | flags.3?true | Whether this transaction is a refund. |
| pending | flags.4?true | The transaction is currently pending. |
| failed | flags.6?true | This transaction has failed. |
| gift | flags.10?true | This transaction was a gift from the user in peer.peer. |
| reaction | flags.11?true | This transaction is a paid reaction ». |
| stargift_upgrade | flags.18?true | This transaction pays for the upgrade of a gift to a collectible gift ». |
| business_transfer | flags.21?true | This transaction transfers stars from the balance of a user account connected to a business bot, to the balance of the business bot, see here » for more info. |
| stargift_resale | flags.22?true | This transaction is related to the resale of a collectible gift ». |
| posts_search | flags.24?true | Represents payment for a paid global post search ». |
| stargift_prepaid_upgrade | flags.25?true | Represents payment for a separate prepaid upgrade of a gift. |
| id | string | Transaction ID. |
| amount | StarsAmount | Amount of Telegram Stars or TON. |
| date | int | Date of the transaction (unixtime). |
| peer | StarsTransactionPeer | Source of the incoming transaction, or its recipient for outgoing transactions. |
| title | flags.0?string | For transactions with bots, title of the bought product. |
| description | flags.1?string | For transactions with bots, description of the bought product. |
| photo | flags.2?WebDocument | For transactions with bots, photo of the bought product. |
| transaction_date | flags.5?int | If neither pending nor failed are set, the transaction was completed successfully, and this field will contain the point in time (Unix timestamp) when the withdrawal was completed successfully. |
| transaction_url | flags.5?string | If neither pending nor failed are set, the transaction was completed successfully, and this field will contain a URL where the withdrawal transaction can be viewed. |
| bot_payload | flags.7?bytes | Bot specified invoice payload (i.e. the payload passed to inputMediaInvoice when creating the invoice). |
| msg_id | flags.8?int | For paid media transactions », message ID of the paid media posted to peer.peer (can point to a deleted message; either way, extended_media will always contain the bought media). |
| extended_media | flags.9?Vector<MessageMedia> | The purchased paid media ». |
| subscription_period | flags.12?int | The number of seconds between consecutive Telegram Star debiting for Telegram Star subscriptions ». |
| giveaway_post_id | flags.13?int | ID of the message containing the messageMediaGiveaway, for incoming star giveaway prizes. |
| stargift | flags.14?StarGift | This transaction indicates a purchase or a sale (conversion back to Stars) of a gift ». |
| floodskip_number | flags.15?int | This transaction is payment for paid bot broadcasts.  Paid broadcasts are only allowed if the allow_paid_floodskip parameter of messages.sendMessage and other message sending methods is set while trying to broadcast more than 30 messages per second to bot users. The integer value returned by this flag indicates the number of billed API calls. |
| starref_commission_permille | flags.16?int | This transaction is the receival (or refund) of an affiliate commission (i.e. this is the transaction received by the peer that created the referral link, flag 17 is for transactions made by users that imported the referral link). |
| starref_peer | flags.17?Peer | For transactions made by referred users, the peer that received the affiliate commission. |
| starref_amount | flags.17?StarsAmount | For transactions made by referred users, the amount of Telegram Stars received by the affiliate, can be negative for refunds. |
| paid_messages | flags.19?int | This transaction is related to the reception or transmission of a paid message ». |
| premium_gift_months | flags.20?int | This transaction indicates the payment for a gifted Telegram Premium subscription ». |
| ads_proceeds_from_date | flags.23?int | Indicates that this is payment for ad revenue from the specified unixtime (always set together with ads_proceeds_to_date). |
| ads_proceeds_to_date | flags.23?int | Indicates that this is payment for ad revenue to the specified unixtime. |


## Type
StarsTransaction

## Related pages
