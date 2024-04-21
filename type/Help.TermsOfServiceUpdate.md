# Help.TermsOfServiceUpdate
Update of Telegram's terms of service

```
help.termsOfServiceUpdateEmpty#e3309f7f expires:int = help.TermsOfServiceUpdate;
help.termsOfServiceUpdate#28ecf961 expires:int terms_of_service:help.TermsOfService = help.TermsOfServiceUpdate;

---functions---

help.getTermsOfServiceUpdate#2ca51fd1 = help.TermsOfServiceUpdate;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| help.termsOfServiceUpdateEmpty | No changes were made to telegram's terms of service |
| help.termsOfServiceUpdate | Info about an update of telegram's terms of service. If the terms of service are declined, then the account.deleteAccount method should be called with the reason "Decline ToS update" |


## Methods
| Method | Description |
| ---- | ----------- |
| help.getTermsOfServiceUpdate | Look for updates of telegram's terms of service |


