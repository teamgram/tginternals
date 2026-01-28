# messages.reportSponsoredMessage
Report a sponsored message », see here » for more info on the full flow.

```
channels.sponsoredMessageReportResultChooseOption#846f9e42 title:string options:Vector<SponsoredMessageReportOption> = channels.SponsoredMessageReportResult;
channels.sponsoredMessageReportResultAdsHidden#3e3bcf2f = channels.SponsoredMessageReportResult;
channels.sponsoredMessageReportResultReported#ad798849 = channels.SponsoredMessageReportResult;
---functions---
messages.reportSponsoredMessage#12cbf0c4 random_id:bytes option:bytes = channels.SponsoredMessageReportResult;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| random_id | bytes | The ad's unique ID. |
| option | bytes | Chosen report option, initially an empty string, see here » for more info on the full flow. |


## Result
channels.SponsoredMessageReportResult

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |

