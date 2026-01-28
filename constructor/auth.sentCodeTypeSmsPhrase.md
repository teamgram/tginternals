# auth.sentCodeTypeSmsPhrase
The code was sent via SMS as a secret phrase starting with the word specified in beginning

```
auth.sentCodeTypeSmsPhrase#b37794af flags:# beginning:flags.0?string = auth.SentCodeType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| beginning | flags.0?string | If set, the secret phrase (and the SMS) starts with this word. |


## Type
auth.SentCodeType

## Related pages
