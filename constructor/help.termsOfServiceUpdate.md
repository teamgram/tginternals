# help.termsOfServiceUpdate
Info about an update of telegram's terms of service. If the terms of service are declined, then the account.deleteAccount method should be called with the reason "Decline ToS update"

```
help.termsOfServiceUpdate#28ecf961 expires:int terms_of_service:help.TermsOfService = help.TermsOfServiceUpdate;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| expires | int | New TOS updates will have to be queried using help.getTermsOfServiceUpdate in expires seconds |
| terms_of_service | help.TermsOfService | New terms of service |


## Type
help.TermsOfServiceUpdate

## Related pages
