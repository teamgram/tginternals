# Telegram passport

Telegram Passport is a unified authorization method for services that require personal identification. Users can upload their documents once, then instantly share their data with services that require real-world ID (finance, ICOs, etc.). Telegram doesn't have access to the users' personal information thanks to end-to-end encryption.

This page describes the request flow that client apps must used to send the requested data to the service.

### Overview

From the perspective of a service that requires real-world ID, the process looks like this:

- A user presses “Log in with Telegram” on your website or in your app.

- You request the data you need.

- The user accepts your privacy policy and agrees to share their data.

- The user's Telegram app downloads and decrypts the data you requested from the end-to-end encrypted storage on Telegram.

- If some of the data you requested is missing, the user can add it to their Telegram Passport at this point.

- The user's app encrypts the data with your public key and sends it to you.

- You decrypt the data, check it for errors and re-request any missing or invalid information.

- You sign the user up for your service. Tada!

See As a bot to see how to request passport data using a bot, through the MTProto API.
Look at the Passport Manual to see how to request passport data using a bot, through the simplified bot API.

From the perspective of a user, the process looks something like this:

- Your app receives an event/intent from one of the SDKs, or from a custom source.

- The user accepts your privacy policy and agrees to share their data.

- The user's Telegram app downloads the data you requested from the end-to-end encrypted storage on Telegram.

- If some of the data you requested is missing, the user can add it to their Telegram Passport at this point.

- The user's app encrypts the data with your public key and sends it to the service.

- You sign the user up for your service. Tada!

See As a user to see how user client apps should send passport data to a service, through the MTProto API.

### As a bot

A simplified version of this process can be used using the bot API, for more info see the Passport Manual.

Using the MTProto API, the process is pretty much the same, up until the actual API calls.

> Note that all binary fields are in raw binary format, unlike in the bot API where they are base64-encoded

#### Setting Up Telegram Passport

As per the bot API.

#### Requesting Information

As per the bot API.

#### Receiving information

Schema:

```
secureData#8aeabec3 data:bytes data_hash:bytes secret:bytes = SecureData;

securePlainPhone#7d6099dd phone:string = SecurePlainData;
securePlainEmail#21ec5a5f email:string = SecurePlainData;

secureFile#7d09c27e id:long access_hash:long size:long dc_id:int date:int file_hash:bytes secret:bytes = SecureFile;

secureValueTypePersonalDetails#9d2a81e3 = SecureValueType;
secureValueTypePassport#3dac6a00 = SecureValueType;
secureValueTypeDriverLicense#6e425c4 = SecureValueType;
secureValueTypeIdentityCard#a0d0744b = SecureValueType;
secureValueTypeInternalPassport#99a48f23 = SecureValueType;
secureValueTypeAddress#cbe31e26 = SecureValueType;
secureValueTypeUtilityBill#fc36954e = SecureValueType;
secureValueTypeBankStatement#89137c0d = SecureValueType;
secureValueTypeRentalAgreement#8b883488 = SecureValueType;
secureValueTypePassportRegistration#99e3806a = SecureValueType;
secureValueTypeTemporaryRegistration#ea02ec33 = SecureValueType;
secureValueTypePhone#b320aadb = SecureValueType;
secureValueTypeEmail#8e3ca7ee = SecureValueType;

secureValue#187fa0ca flags:# type:SecureValueType data:flags.0?SecureData front_side:flags.1?SecureFile reverse_side:flags.2?SecureFile selfie:flags.3?SecureFile translation:flags.6?Vector<SecureFile> files:flags.4?Vector<SecureFile> plain_data:flags.5?SecurePlainData hash:bytes = SecureValue;

secureCredentialsEncrypted#33f0ea47 data:bytes hash:bytes secret:bytes = SecureCredentialsEncrypted;

messageActionSecureValuesSentMe#1b287353 values:Vector<SecureValue> credentials:SecureCredentialsEncrypted = MessageAction; 
messageService#7a800e0a flags:# out:flags.1?true mentioned:flags.4?true media_unread:flags.5?true reactions_are_possible:flags.9?true silent:flags.13?true post:flags.14?true legacy:flags.19?true id:int from_id:flags.8?Peer peer_id:Peer saved_peer_id:flags.28?Peer reply_to:flags.3?MessageReplyHeader date:int action:MessageAction reactions:flags.20?MessageReactions ttl_period:flags.25?int = Message;

updateNewMessage#1f2b0afd message:Message pts:int pts_count:int = Update;
```

When the user confirms your request by pressing the "Authorize" button, the MTProto API sends an updateNewMessage from the user, with a messageService constructor, containing a messageActionSecureValuesSentMe constructor that contains the encrypted Telegram Passport data.

#### Decrypting data

```
secureCredentialsEncrypted#33f0ea47 data:bytes hash:bytes secret:bytes = SecureCredentialsEncrypted;

messageActionSecureValuesSentMe#1b287353 values:Vector<SecureValue> credentials:SecureCredentialsEncrypted = MessageAction;
```

To decrypt the received data, first, decrypt the credentials contained in secureCredentialsEncrypted.

> Note that all hashes are raw binary data, not hexits

#### Credentials

The credentials are a JSON-serialized object, structured exactly as in the bot API ».
Since decryption credentials are E2E encrypted, apps have to store the decryption credentials as JSON and not TL payloads.

The credentials are used as described in the Passport Manual to decrypt the files attached to the secureValue.
In this case, the container for the E2E encrypted data is in TL, while the encrypted data itself is in JSON.

##### secureValue

```
secureValue#187fa0ca flags:# type:SecureValueType data:flags.0?SecureData front_side:flags.1?SecureFile reverse_side:flags.2?SecureFile selfie:flags.3?SecureFile translation:flags.6?Vector<SecureFile> files:flags.4?Vector<SecureFile> plain_data:flags.5?SecurePlainData hash:bytes = SecureValue;

messageActionSecureValuesSentMe#1b287353 values:Vector<SecureValue> credentials:SecureCredentialsEncrypted = MessageAction;
```

The schema for the secureValue constructor defines the constructor that can be found in each field.

Here's a list of possible SecureValueTypes, and the parameters that can be set/requested when using each type.

##### SecureData

```
secureData#8aeabec3 data:bytes data_hash:bytes secret:bytes = SecureData;
```

Data is an encrypted and padded JSON-serialized object of one of the specified JSON types, depending on the chosen type.

DataCredentials extracted from the credentials can then be used to decrypt encrypted data from the data field in secureData.
For more info on how to decrypt the data field, see the passport manual.

##### SecureFile

```
secureFile#7d09c27e id:long access_hash:long size:long dc_id:int date:int file_hash:bytes secret:bytes = SecureFile;    

inputSecureFileLocation#cbc7ee28 id:long access_hash:long = InputFileLocation;

---functions---

upload.getFile#be5335be flags:# precise:flags.0?true cdn_supported:flags.1?true location:InputFileLocation offset:long limit:int = upload.File;
```

Files (JPG format when decrypted, max. 10 MB) are downloaded chunk by chunk as described in files », except that instead of generating an inputFileLocation, an inputFileLocation should be generated, instead.

- The id field is the id of the secureFile

- The access_hash field is the access_hash of the secureFile

FileCredentials extracted from the credentials can then be used to decrypt downloaded encrypted data.
For more info on how to decrypt passport files, see the passport manual.

##### SecurePlainData

```
securePlainPhone#7d6099dd phone:string = SecurePlainData;
securePlainEmail#21ec5a5f email:string = SecurePlainData;
```

The email/phone is passed in plaintext using the respective SecurePlainData constructor.
Emails and phone numbers sent using telegram passport are already verified as described in the passport manual.

#### Fixing errors

```
secureValueErrorData#e8a40bd9 type:SecureValueType data_hash:bytes field:string text:string = SecureValueError;
secureValueErrorFrontSide#be3dfa type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorReverseSide#868a2aa5 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorSelfie#e537ced6 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorFile#7a700873 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorFiles#666220e9 type:SecureValueType file_hash:Vector<bytes> text:string = SecureValueError;
secureValueError#869d758f type:SecureValueType hash:bytes text:string = SecureValueError;
secureValueErrorTranslationFile#a1144770 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorTranslationFiles#34636dd8 type:SecureValueType file_hash:Vector<bytes> text:string = SecureValueError;

inputUser#f21158c6 user_id:long access_hash:long = InputUser;


---functions---

users.setSecureValueErrors#90c894b5 id:InputUser errors:Vector<SecureValueError> = Bool;
```

If the data you received contains errors, the bot can use the users.setSecureValueErrors method to inform the user and request information again. The user will not be able to resend the data, until all errors are fixed.

Descriptions of the method parameters can be found in the method's documentation page ».

### As a user

#### Receiving requests

The process starts when your app receives an event from one of the SDKs, or from a custom source.

#### URI format

The SDKs trigger a passport authorization request by opening the following deep links »:

tg: syntax:

```
tg://passport?bot_id=<bot_user_id>&scope=<scope>&public_key=<public_key>&nonce=<nonce>
tg://resolve?domain=telegrampassport&bot_id=<bot_user_id>&scope=<scope>&public_key=<public_key>&nonce=<nonce>
```

With the following query string parameters:

Example URI, generated by the Telegram Passport Example page:

```
tg://resolve?domain=telegrampassport&bot_id=543260180&scope=%7B%22v%22%3A1%2C%22d%22%3A%5B%7B%22_%22%3A%22pd%22%2C%22n%22%3A1%7D%2C%22ad%22%2C%22pn%22%2C%22em%22%2C%7B%22_%22%3A%5B%7B%22_%22%3A%22pp%22%2C%22s%22%3A1%2C%22t%22%3A1%7D%2C%22ip%22%2C%22dl%22%2C%22ic%22%5D%7D%2C%7B%22_%22%3A%5B%22ub%22%2C%22bs%22%2C%22ra%22%2C%22pr%22%2C%22tr%22%5D%7D%5D%7D&public_key=-----BEGIN%20PUBLIC%20KEY-----%0AMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAv6m1zBF8lZOCqcxf8hnj%0AkvHwuWdU8s4rBWaxKXH%2FvDDUklcCS5uhSnmjhxWca9suubaG3lW4HxlCilkeJPVf%0Ajimg5Q8ZqWrR3OoOihEpcG9iJZTOEpsEk7VtEiabgacBG3Quv9JslTrDe95Fn801%0At9d21HXwgMrHeHpWDOn31Dr%2BwoEH%2BkwySUWa6L%2FZbnGwSNP7eeDTE7Amz1RMDk3t%0A8EWGq58u0IQatPcEH09aUQlKzk6MIiALkZ9ILBKCBk6d2WCokKnsdBctovNbxwSx%0AhP1qst1r%2BYc8iPBZozsDC0ZsC5jXCkcODI3OC0tkNtYzN2XKalW5R0DjDRUDmGhT%0AzQIDAQAB%0A-----END%20PUBLIC%20KEY-----%0A&nonce=b8e892dc2e0afe63424d101b964f1256_32858210_708614a4585b84872e&callback_url=https%3A%2F%2Fcore.telegram.org%2Fpassport%2Fexample%3Fpassport_ssid%3Db8e892dc2e0afe63424d101b964f1256_32858210_db259b427f200751ce&payload=b8e892dc2e0afe63424d101b964f1256_32858210_708614a4585b84872e
```

#### UriPassportScope

This object represents the data to be requested.

##### UriPassportScopeElement

This object represents a requested element, should be one of:

- UriPassportScopeElementOneOfSeveral - use to request any one of the documents included in the scope.

- UriPassportScopeElementOne – use to request one particular document.

Passport document type identifiers are aliased with the following reduced type identifiers:

You can use the special type "idd" as an alias for one of "pp", "dl", "ic" and the special type "add" as an alias for one of "ub", "bs", "ra".

#### UriPassportScopeElementOneOfSeveral

This object represents several elements one of which must be provided.

#### UriPassportScopeElementOne

This object represents one particular element that must be provided. If no options are needed, String can be used instead of this object to specify the type of the element.

You can also use the special type "idd" as an alias for one of "pp", "dl", "ic" and the special type "add" as an alias for one of "ub", "bs", "ra".

#### Setting up Telegram Passport

The next step for the client app is to request the user's 2FA passport, and configure Telegram Passport/fetch and decrypt remotely saved Telegram Passport parameters as described in the Encryption article ».

#### Fetching the passport form

```
account.authorizationForm#ad2e1cd8 flags:# required_types:Vector<SecureRequiredType> values:Vector<SecureValue> errors:Vector<SecureValueError> users:Vector<User> privacy_policy_url:flags.0?string = account.AuthorizationForm;

---functions---

account.getAuthorizationForm#a929597a bot_id:long scope:string public_key:string = account.AuthorizationForm;
```

Then, the client app passes the bot ID, scope and public key from the passport authorization request to the Telegram servers using the account.getAuthorizationForm method.

The response will be an account.authorizationForm constructor, with info about the required document types, the URL of the service's privacy policy, as well as info about the bot to which the form should be sent.
If the form was already submitted at least once, the constructor will also contain a list of already submitted data, along with eventual errors.

The user should accept the privacy policy and proceed to fill in the required data, and the client should encrypt and upload it as described in the Encryption article ».

#### Submitting the passport form

```
secureCredentialsEncrypted#33f0ea47 data:bytes hash:bytes secret:bytes = SecureCredentialsEncrypted;

secureValueHash#ed1ecdb0 type:SecureValueType hash:bytes = SecureValueHash;

---functions---

account.acceptAuthorization#f3ed4c73 bot_id:long scope:string public_key:string value_hashes:Vector<SecureValueHash> credentials:SecureCredentialsEncrypted = Bool;
```

Once the user finishes uploading the required documents and clicks on the submit button, the client calls account.acceptAuthorization, submitting the documents to the bot associated to the service.

- As before, bot_id, scope and public_key are taken from the authorization request URI.

- value_hashes is used by the server to choose which document of which type to send to the bot: the type field should be set to the document type, and the hash field should be set to the data_hash/file_hash generated when uploading encrypting the data ».

- credentials contains the encrypted credentials required by the service to decrypt the sent E2E encrypted secure values: it is generated as described in Passport Credentials ».

Finally, the client opens the callback URL (if present).

#### Handling invalid forms

```
secureValueErrorData#e8a40bd9 type:SecureValueType data_hash:bytes field:string text:string = SecureValueError;
secureValueErrorFrontSide#be3dfa type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorReverseSide#868a2aa5 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorSelfie#e537ced6 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorFile#7a700873 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorFiles#666220e9 type:SecureValueType file_hash:Vector<bytes> text:string = SecureValueError;
secureValueError#869d758f type:SecureValueType hash:bytes text:string = SecureValueError;
secureValueErrorTranslationFile#a1144770 type:SecureValueType file_hash:bytes text:string = SecureValueError;
secureValueErrorTranslationFiles#34636dd8 type:SecureValueType file_hash:Vector<bytes> text:string = SecureValueError;

account.authorizationForm#ad2e1cd8 flags:# required_types:Vector<SecureRequiredType> values:Vector<SecureValue> errors:Vector<SecureValueError> users:Vector<User> privacy_policy_url:flags.0?string = account.AuthorizationForm;

---functions---

account.getAuthorizationForm#a929597a bot_id:long scope:string public_key:string = account.AuthorizationForm;
```

If any of the values of the submitted form are rejected by the service, the bot calls the appropriate method to set information about errors.

The user can find out about these errors directly from the service, or, if they decide to restart the process and resend the corrected data, directly from the authorization form (errors field).

