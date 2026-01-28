# auth.sentCodePaymentRequired
Official apps may receive this constructor, indicating that due to the high cost of SMS verification codes for the user's country/provider, the user must purchase a Telegram Premium subscription in order to proceed with the login/signup.

```
auth.sentCodePaymentRequired#d7a2fcf9 store_product:string phone_code_hash:string support_email_address:string support_email_subject:string = auth.SentCode;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| store_product | string | Store identifier of the Telegram Premium subscription. |
| phone_code_hash | string | Phone code hash, to be stored and later re-used with auth.signIn |
| support_email_address | string | An email address that can be contacted for more information about this request. |
| support_email_subject | string | The mandatory subject for the email. |


## Type
auth.SentCode

## Related pages
