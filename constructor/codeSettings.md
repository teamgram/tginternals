# codeSettings
Settings used by telegram servers for sending the confirm code.

```
codeSettings#ad253d78 flags:# allow_flashcall:flags.0?true current_number:flags.1?true allow_app_hash:flags.4?true allow_missed_call:flags.5?true allow_firebase:flags.7?true logout_tokens:flags.6?Vector<bytes> token:flags.8?string app_sandbox:flags.8?Bool = CodeSettings;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| allow_flashcall | flags.0?true | Whether to allow phone verification via phone calls. |
| current_number | flags.1?true | Pass true if the phone number is used on the current device. Ignored if allow_flashcall is not set. |
| allow_app_hash | flags.4?true | If a token that will be included in eventually sent SMSs is required: required in newer versions of android, to use the android SMS receiver APIs |
| allow_missed_call | flags.5?true | Whether this device supports receiving the code using the auth.codeTypeMissedCall method |
| allow_firebase | flags.7?true | Whether Firebase auth is supported |
| logout_tokens | flags.6?Vector<bytes> | Previously stored future auth tokens, see the documentation for more info » |
| token | flags.8?string | Used only by official iOS apps for Firebase auth: device token for apple push. |
| app_sandbox | flags.8?Bool | Used only by official iOS apps for firebase auth: whether a sandbox-certificate will be used during transmission of the push notification. |


## Type


## Related pages
