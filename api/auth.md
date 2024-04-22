# 用户授权

授权与客户端的加密密钥标识相关联：auth_key_id。在授权后不需要传递额外的参数给方法。

要以机器人身份登录，请按照以下说明进行»。

还提供了基于备用 QR 码的登录流程»。

### 发送验证码

示例实现：Telegram for Android、tdlib。

要显示一个格式良好且经过验证的电话号码字段，可以使用 help.getCountriesList 方法获取 help.countriesList 构造函数。
然后，help.countriesList 配置和其他配置值将如下所述使用»。

然后，使用 auth.sendCode 向用户的电话发送包含授权码的文本消息。
然而，如果将来使用了授权令牌，则情况并非总是如此：

#### 将来的授权令牌

在先前授权的会话上调用 auth.logOut 时，服务器可能会返回一个 future_auth_token，应将其存储在本地数据库中。
在登录时，auth.authorization 返回的 auth.authorization 中也包含一个 future_auth_token。
在任何时候，将来的授权令牌数据库应该最多包含 20 个令牌：随着新令牌的添加，将老令牌驱逐以保持在此限制以下。
在调用 auth.sendCode 时，应该将数据库中存在的所有将来的授权令牌提供给 codeSettings.logout_tokens。
如果任何将来的授权令牌与我们正在尝试登录的帐户匹配且令牌尚未过期：

- 如果未启用双重身份验证，auth.sendCode 将直接返回一个带有会话信息的 auth.sentCodeSuccess 构造函数，指示会话已被授权。

- 如果启用了双重身份验证，auth.sendCode 将返回一个 SESSION_PASSWORD_NEEDED 的 RPC 错误，要求用户输入双重身份验证密码，而不发送任何授权码。

否则，系统将根据以下逻辑发送授权码：

#### 码类型

```
codeSettings#ad253d78 flags:# allow_flashcall:flags.0?true current_number:flags.1?true allow_app_hash:flags.4?true allow_missed_call:flags.5?true allow_firebase:flags.7?true logout_tokens:flags.6?Vector<bytes> token:flags.8?string app_sandbox:flags.8?Bool = CodeSettings;

auth.sentCodeTypeApp#3dbb5986 length:int = auth.SentCodeType;
auth.sentCodeTypeSms#c000bba2 length:int = auth.SentCodeType;
auth.sentCodeTypeCall#5353e5a7 length:int = auth.SentCodeType;
auth.sentCodeTypeFlashCall#ab03c6d9 pattern:string = auth.SentCodeType;
auth.sentCodeTypeMissedCall#82006484 prefix:string length:int = auth.SentCodeType;
auth.sentCodeTypeEmailCode#f450f59b flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true email_pattern:string length:int reset_available_period:flags.3?int reset_pending_date:flags.4?int = auth.SentCodeType;
auth.sentCodeTypeSetUpEmailRequired#a5491dea flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true = auth.SentCodeType;
auth.sentCodeTypeFragmentSms#d9565c39 url:string length:int = auth.SentCodeType;
auth.sentCodeTypeFirebaseSms#e57b1432 flags:# nonce:flags.0?bytes receipt:flags.1?string push_timeout:flags.1?int length:int = auth.SentCodeType;

auth.sentCode#5e002502 flags:# type:auth.SentCodeType phone_code_hash:string next_type:flags.1?auth.CodeType timeout:flags.2?int = auth.SentCode;
auth.sentCodeSuccess#2390fe44 authorization:auth.Authorization = auth.SentCode;

---functions---

auth.sendCode#a677244f phone_number:string api_id:int api_hash:string settings:CodeSettings = auth.SentCode;
auth.resendCode#3ef1a9bf phone_number:string phone_code_hash:string = auth.SentCode;

auth.requestFirebaseSms#89464b50 flags:# phone_number:string phone_code_hash:string safety_net_token:flags.0?string ios_push_secret:flags.1?string = Bool;
```

auth.sendCode 方法有参数用于启用/禁用闪电电话和未接来电的使用，并允许传递一个 SMS 令牌，该令牌将包含在发送的 SMS 中。
例如，后者在较新版本的 Android 中是必需的，以使用 Android SMS 接收器 API。

返回的 auth.sentCode 对象将包含多个参数：

系统将自动选择如何发送授权码；授权码可能会以多种方式到达，通过 auth.SentCodeType 构造函数的 type 字段向客户端表示。

请注意，在某些情况下，当使用短信代码/通话进行注册或登录时，可能只能使用 auth.sentCodeTypeFirebaseSms 码类型。
目前，只有官方应用程序可以使用 Firebase 短信认证：这意味着在某些情况下，只有官方应用程序才能通过短信/通话接收登录/注册代码。
第三方应用程序可以使用任何其他代码交付方式（Telegram 代码、片段代码、电子邮件代码、将来的授权令牌、QR 码）登录。

- auth.sentCodeTypeSetUpEmailRequired：如果用户经常登录，Telegram 将要求用户验证一个用于发送登录码的电子邮件。

- 有关验证过程的更多信息，请参见此处»。

- auth.sentCodeTypeEmailCode：验证码已发送到配置的登录电子邮件。

- auth.sentCodeTypeFragmentSms：通过 fragment.com 发送了验证码：打开指定的 URL 以使用您的钱包登录 Fragment 平台并查看验证码。

- auth.sentCodeTypeApp：将代码作为 Telegram 服务通知发送给所有其他已登录的会话。

- auth.sentCodeTypeFirebaseSms：Firebase 登录流程，仅限官方应用。

- 在 Android 上，只有在设置了 codeSettings.allow_firebase 标志时才能接收。

- 客户端必须将接收到的 auth.sentCodeTypeFirebaseSms.nonce 传递给 SafetyNet Attestation API，然后将获得的 JWS 对象传递给 auth.requestFirebaseSms.safety_net_token，以及电话号码和电话代码哈希。

- 如果该方法返回 boolTrue，则代码将通过短信发送；否则，必须使用 next_type 认证方法，并使用 auth.resendCode。

- 在 iOS 上，只有在将 Apple 推送的设备令牌传递给 codeSettings.token 时才能接收。

- 然后，客户端等待新的推送通知，以在 auth.sentCodeTypeFirebaseSms.push_timeout 秒内接收。

- 如果在 push_timeout 秒内未收到推送通知，则必须使用 next_type 认证方法，并使用 auth.resendCode。

- 如果收到具有 receipt 和 ios_push_secret 字段的推送通知，并且 receipt 字段的值与 codeSettings.receipt 匹配，则将 ios_push_secret 的值传递给 auth.requestFirebaseSms.ios_push_secret，以及电话号码和电话代码哈希。

- 如果该方法返回 boolTrue，则代码将通过短信发送；否则，必须使用 next_type 认证方法，并使用 auth.resendCode。

- auth.sentCodeTypeSms：通过短信发送了代码。

- auth.sentCodeTypeCall：用户将收到一通电话，合成语音会告诉用户验证码以输入。

- auth.sentCodeTypeFlashCall：代码将通过闪光电话呼叫发送，并立即关闭。

- 在这种情况下，电话代码将是电话号码本身，只需确保电话号码与指定的模式匹配（参见 auth.sentCodeTypeFlashCall）。

- auth.sentCodeTypeMissedCall：代码将通过闪光电话呼叫发送，并立即关闭。

- 来电的电话号码的最后几位是用户必须手动输入的代码。

- 将来的授权令牌»

如果消息在一定时间内（超时秒数）未到达手机，则可以调用 auth.resendCode 方法重新发送 next_type 类型的代码。
如果再次发生相同的情况，可以使用上一次调用 auth.resendCode 返回的 next_type 调用 auth.resendCode。
要取消验证代码，请使用 auth.cancelCode。

### 电子邮件验证

```
auth.sentCodeTypeSetUpEmailRequired#a5491dea flags:# apple_signin_allowed:flags.0?true google_signin_allowed:flags.1?true = auth.SentCodeType;

emailVerifyPurposeLoginSetup#4345be73 phone_number:string phone_code_hash:string = EmailVerifyPurpose;

emailVerificationCode#922e55a9 code:string = EmailVerification;
emailVerificationGoogle#db909ec2 token:string = EmailVerification;
emailVerificationApple#96d074fd token:string = EmailVerification;

account.sentEmailCode#811f854f email_pattern:string length:int = account.SentEmailCode;

account.emailVerifiedLogin#e1bb0d61 email:string sent_code:auth.SentCode = account.EmailVerified;

emailVerifyPurposeLoginChange#527d22eb = EmailVerifyPurpose;
account.emailVerified#2b96cd1b email:string = account.EmailVerified;

---functions---

account.sendVerifyEmailCode#98e037bb purpose:EmailVerifyPurpose email:string = account.SentEmailCode;
account.verifyEmail#32da4cf purpose:EmailVerifyPurpose verification:EmailVerification = account.EmailVerified;
auth.resetLoginEmail#7e960193 phone_number:string phone_code_hash:string = auth.SentCode;
```

Telegram 可能会在 auth.sendCode 返回的 auth.sentCode 构造函数中返回一个 auth.sentCodeTypeSetUpEmailRequired 码类型。
在这种情况下，客户端应要求用户验证一个电子邮件地址，该地址将用于接收登录码，方法如下：

- 如果设置了 google_signin_allowed 或 apple_signin_allowed 标志，则用户可以直接按照此处指定的方式（Google ID）» 和此处（Apple ID）» 使用 Google/Apple ID 验证其电子邮件。

- 在获取 ID 令牌后，调用 account.verifyEmail，提供以下参数：

- purpose - 一个 emailVerifyPurposeLoginSetup 构造函数

- purpose.phone_number - 与 auth.sendCode 一起使用的电话号码

- purpose.phone_code_hash - 包含在 auth.sendCode 返回的 auth.sentCode 构造函数中的电话代码哈希

- verification - emailVerificationGoogle 或 emailVerificationApple

- verification.token - Google ID API 返回的 ID 令牌。

- 成功后，account.verifyEmail 方法将返回一个带有 auth.sentCode 构造函数的 account.emailVerifiedLogin 构造函数，应该像平常一样处理»。

- 否则，要求用户输入电子邮件地址，然后调用 account.sendVerifyEmailCode，提供以下参数：

- email - 电子邮件地址

- purpose - 一个 emailVerifyPurposeLoginSetup 构造函数

- purpose.phone_number - 与 auth.sendCode 一起使用的电话号码

- purpose.phone_code_hash - 包含在 auth.sendCode 返回的 auth.sentCode 构造函数中的电话代码哈希

- 一旦用户收到并输入了验证代码，就调用 account.verifyEmail，提供以下参数：

- purpose - 一个 emailVerifyPurposeLoginSetup 构造函数

- purpose.phone_number - 与 auth.sendCode 一起使用的电话号码

- purpose.phone_code_hash - 包含在 auth.sendCode 返回的 auth.sentCode 构造函数中的电话代码哈希

- verification - emailVerificationCode

- verification.code - 用户收到的验证代码。

- 成功后，account.verifyEmail 方法将返回一个带有 auth.sentCode 构造函数的 account.emailVerifiedLogin 构造函数，应该像平常一样处理»。

如果用户无法访问其电子邮件地址，则可以使用 auth.resetLoginEmail 请求电子邮件重置。

在登录后更改登录电子邮件时，请将 emailVerifyPurposeLoginChange 作为目的传递，按照与上述相同的 Google ID/Apple ID/电子邮件代码登录流程：成功后，account.verifyEmail 方法将返回一个 account.emailVerified 构造函数。

### 登录/注册

当用户输入验证代码时，必须使用 auth.signIn 方法验证它并可能登录用户。

如果代码输入正确，但方法返回 auth.authorizationSignUpRequired，则表示尚不存在具有此电话号码的帐户：用户需要提供基本信息，接受服务条款，然后必须调用新用户注册方法（auth.signUp）。

### 双重身份验证

尝试使用 auth.signIn 进行登录时，如果用户已启用双重身份验证，则可能会返回错误 400 SESSION_PASSWORD_NEEDED。
在这种情况下，必须遵循 SRP 双重身份验证的说明。

要在已经授权的帐户上设置双重身份验证，请遵循 SRP 双重身份验证文档。

### 确认登录

```
authorization#ad01d61d flags:# current:flags.0?true official_app:flags.1?true password_pending:flags.2?true encrypted_requests_disabled:flags.3?true call_requests_disabled:flags.4?true unconfirmed:flags.5?true hash:long device_model:string platform:string system_version:string api_id:int app_name:string app_version:string date_created:int date_active:int ip:string country:string region:string = Authorization;

account.authorizations#4bff8ea0 authorization_ttl_days:int authorizations:Vector<Authorization> = account.Authorizations;

updateNewAuthorization#8951abef flags:# unconfirmed:flags.0?true hash:long date:flags.0?int device:flags.0?string location:flags.0?string = Update;

---functions---

account.getAuthorizations#e320c158 = account.Authorizations;

account.changeAuthorizationSettings#40f48462 flags:# confirmed:flags.3?true hash:long encrypted_requests_disabled:flags.0?Bool call_requests_disabled:flags.1?Bool = Bool;

account.resetAuthorization#df77f3bc hash:long = Bool;
```

登录时，其他已登录的会话将收到一个 updateNewAuthorization 更新。
如果设置了 unconfirmed 标志，则客户端应显示一个通知，询问用户是否认可该会话。

如果用户点击“是”按钮，请调用 account.changeAuthorizationSettings，其中包含新会话的哈希和已确认标志，确认指定的会话。

如果用户点击“否”按钮，请调用 account.resetAuthorization，其中包含新会话的哈希，注销指定的会话。

如果用户没有采取任何行动，则会话将在登录后的 authorization_autoconfirm_period 秒后自动确认（请参阅相关的客户端配置参数»）。

### 使登录代码失效

如果用户将登录代码发送到另一个 Telegram 聊天中，无论是转发还是将其发送在消息中，Telegram 的服务器都会自动使其失效：但是，如果用户尝试截屏或转发登录通知服务用户（ID 777000）发送的消息中包含的登录代码，则客户端也应该手动立即使登录代码失效。

如果收到的消息：

- 由登录通知服务用户（ID 777000）发送

- 并且是文本消息（不是媒体）

- 并且包含一个或多个登录代码，定义为 5 到 7 位十进制数字序列，可选地与或后跟任意数量的 - 字符（示例实现»）

被用户截屏或转发到任何聊天中

应调用 account.invalidateSignInCodes，传递提取的登录代码（不包括任何 - 字符）。

```
---functions---

account.invalidateSignInCodes#ca8ae8ba codes:Vector<string> = Bool;
```

### 测试帐户

每个电话号码每天仅限于一定数量的登录次数（例如，5 次，但这可能会更改），之后 API 将返回一个洪水错误，直到第二天。这可能不足以测试客户端应用程序中的用户授权流程的实现。

有几个保留的电话号码前缀，用于测试应用程序是否正确处理 DC 之间的重定向、注册、登录和双重身份验证流程。这些号码仅在测试 DC 上可用（它们的 TCP 传输的 IP 地址在获得 api_id 后的 API 开发工具面板中可用，HTTPS/WebSocket 传输的 URI 格式）。

如果要模拟与 DC 编号 X 关联的用户应用程序，只需在注册用户时将电话号码指定为 99966XYYYY，其中 YYYY 是随机数字。这样的用户将始终获得 XXXXX 作为登录确认代码（DC 编号，重复五次）。请注意，X 的值必须在 1-3 范围内，因为只有 3 个测试 DC。当特定测试号码达到洪水限制时，只需选择另一个号码（更改 YYYY 随机部分）。

不要在此类测试帐户的消息中存储任何重要或私人信息；任何人都可以利用简化的授权机制 - 我们定期删除其中存储的所有信息。

只有少部分 API 方法对未经授权的用户可用：

- auth.sendCode

- auth.resendCode

- account.getPassword

- auth.checkPassword

- auth.checkPhone

- auth.signUp

- auth.signIn

- auth.importAuthorization

- help.getConfig

- help.getNearestDc

- help.getAppUpdate

- help.getCdnConfig

- langpack.getLangPack

- langpack.getStrings

- langpack.getDifference

- langpack.getLanguages

- langpack.getLanguage

其他方法将导致错误：401 UNAUTHORIZED。
