# auth.CodeType
Type of verification code that will be sent next if you call the resendCode method

```
auth.codeTypeSms#72a3158c = auth.CodeType;
auth.codeTypeCall#741cd3e3 = auth.CodeType;
auth.codeTypeFlashCall#226ccefb = auth.CodeType;
auth.codeTypeMissedCall#d61ad6ee = auth.CodeType;
auth.codeTypeFragmentSms#6ed998c = auth.CodeType;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| auth.codeTypeSms | The next time, the authentication code will be delivered via an immediately canceled incoming call. |
| auth.codeTypeCall | The next time, the authentication code is to be delivered via an outgoing phone call. |
| auth.codeTypeFlashCall | The next time, the authentication code will be delivered via an immediately canceled incoming call. |
| auth.codeTypeMissedCall | The next time, the authentication code will be delivered via an immediately canceled incoming call, handled manually by the user. |
| auth.codeTypeFragmentSms | The next time, the authentication code will be delivered via fragment.com |


## Methods
| Method | Description |
| ---- | ----------- |


