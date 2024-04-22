# auth.SentCode
Contains info on a confirmation code message sent via SMS, phone call or Telegram.

```
auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;

---functions---

auth.sendCode#a677244f phone_number:string api_id:int api_hash:string settings:CodeSettings = auth.SentCode;
auth.resendCode#3ef1a9bf phone_number:string phone_code_hash:string = auth.SentCode;
auth.resetLoginEmail#7e960193 phone_number:string phone_code_hash:string = auth.SentCode;

account.sendChangePhoneCode#82574ae5 phone_number:string settings:CodeSettings = auth.SentCode;
account.sendConfirmPhoneCode#1b3faa88 hash:string settings:CodeSettings = auth.SentCode;
account.sendVerifyPhoneCode#a5a356f9 phone_number:string settings:CodeSettings = auth.SentCode;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| auth.sentCode | Contains info about a sent verification code. |
| auth.sentCodeSuccess | The user successfully authorized using future auth tokens |


## Methods
| Method | Description |
| ---- | ----------- |
| auth.sendCode | Send the verification code for login |
| account.sendChangePhoneCode | Verify a new phone number to associate to the current account |
| auth.resendCode | Resend the login code via another medium, the phone code type is determined by the return value of the previous auth.sendCode/auth.resendCode: see login for more info. |
| account.sendConfirmPhoneCode | Send confirmation code to cancel account deletion, for more info click here » |
| account.sendVerifyPhoneCode | Send the verification phone code for telegram passport. |
| auth.resetLoginEmail | Reset the login email ». |


