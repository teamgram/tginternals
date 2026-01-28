# channels.SponsoredMessageReportResult
Status of the method call used to report a sponsored message ».

```
channels.sponsoredMessageReportResultChooseOption#846f9e42 title:string options:Vector<SponsoredMessageReportOption> = channels.SponsoredMessageReportResult;
channels.sponsoredMessageReportResultAdsHidden#3e3bcf2f = channels.SponsoredMessageReportResult;
channels.sponsoredMessageReportResultReported#ad798849 = channels.SponsoredMessageReportResult;

---functions---

messages.reportSponsoredMessage#12cbf0c4 random_id:bytes option:bytes = channels.SponsoredMessageReportResult;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| channels.sponsoredMessageReportResultChooseOption | The user must choose a report option from the localized options available in options, and after selection, channels.reportSponsoredMessage must be invoked again, passing the option's option field to the option param of the method. |
| channels.sponsoredMessageReportResultAdsHidden | Sponsored messages were hidden for the user in all chats. |
| channels.sponsoredMessageReportResultReported | The sponsored message was reported successfully. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.reportSponsoredMessage | Report a sponsored message », see here » for more info on the full flow. |


