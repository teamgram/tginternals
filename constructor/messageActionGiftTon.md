# messageActionGiftTon
You were gifted some toncoins.

```
messageActionGiftTon#a8a3c699 flags:# currency:string amount:long crypto_currency:string crypto_amount:long transaction_id:flags.0?string = MessageAction;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| currency | string | Name of a localized FIAT currency. |
| amount | long | FIAT currency equivalent (in the currency specified in currency) of the amount specified in crypto_amount. |
| crypto_currency | string | Name of the cryptocurrency. |
| crypto_amount | long | Amount in the smallest unit of the cryptocurrency (for TONs, one billionth of a ton, AKA a nanoton). |
| transaction_id | flags.0?string | Transaction ID. |


## Type


## Related pages
