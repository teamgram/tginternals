# auth.sentCodeTypeSmsWord
The code was sent via SMS as a secret word, starting with the letter specified in beginning

```
auth.sentCodeTypeSmsWord#a416ac81 flags:# beginning:flags.0?string = auth.SentCodeType;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| beginning | flags.0?string | If set, the secret word in the sent SMS (which may contain multiple words) starts with this letter. |


## Type
auth.SentCodeType

## Related pages
