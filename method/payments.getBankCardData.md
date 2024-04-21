# payments.getBankCardData
Get info about a credit card

```
payments.bankCardData#3e24e573 title:string open_urls:Vector<BankCardOpenUrl> = payments.BankCardData;
---functions---
payments.getBankCardData#2e79d779 number:string = payments.BankCardData;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| number | string | Credit card number |


## Result
payments.BankCardData

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BANK_CARD_NUMBER_INVALID | The specified card number is invalid. |

