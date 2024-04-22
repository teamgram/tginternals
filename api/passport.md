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

When the user confirms your request by pressing the "Authorize" button, the MTProto API sends an updateNewMessage from the user, with a messageService constructor, containing a messageActionSecureValuesSentMe constructor that contains the encrypted Telegram Passport data.

#### Decrypting data

To decrypt the received data, first, decrypt the credentials contained in secureCredentialsEncrypted.

> Note that all hashes are raw binary data, not hexits

#### Credentials

The credentials are a JSON-serialized object, structured exactly as in the bot API ».
Since decryption credentials are E2E encrypted, apps have to store the decryption credentials as JSON and not TL payloads.

The credentials are used as described in the Passport Manual to decrypt the files attached to the secureValue.
In this case, the container for the E2E encrypted data is in TL, while the encrypted data itself is in JSON.

##### secureValue

The schema for the secureValue constructor defines the constructor that can be found in each field.

Here's a list of possible SecureValueTypes, and the parameters that can be set/requested when using each type.

##### SecureData

Data is an encrypted and padded JSON-serialized object of one of the specified JSON types, depending on the chosen type.

DataCredentials extracted from the credentials can then be used to decrypt encrypted data from the data field in secureData.
For more info on how to decrypt the data field, see the passport manual.

##### SecureFile

Files (JPG format when decrypted, max. 10 MB) are downloaded chunk by chunk as described in files », except that instead of generating an inputFileLocation, an inputFileLocation should be generated, instead.

- The id field is the id of the secureFile

- The access_hash field is the access_hash of the secureFile

FileCredentials extracted from the credentials can then be used to decrypt downloaded encrypted data.
For more info on how to decrypt passport files, see the passport manual.

##### SecurePlainData

The email/phone is passed in plaintext using the respective SecurePlainData constructor.
Emails and phone numbers sent using telegram passport are already verified as described in the passport manual.

#### Fixing errors

If the data you received contains errors, the bot can use the users.setSecureValueErrors method to inform the user and request information again. The user will not be able to resend the data, until all errors are fixed.

Descriptions of the method parameters can be found in the method's documentation page ».

### As a user

#### Receiving requests

The process starts when your app receives an event from one of the SDKs, or from a custom source.

#### URI format

The SDKs trigger a passport authorization request by opening the following deep links »:

tg: syntax:

With the following query string parameters:

Example URI, generated by the Telegram Passport Example page:

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

The next step for the client app is to request the user's 2FA passport, and configure Telegram Passport/fetch and decrypt remotely saved Telegram Passport parameters as described in the Encryption article ».

#### Fetching the passport form

Then, the client app passes the bot ID, scope and public key from the passport authorization request to the Telegram servers using the account.getAuthorizationForm method.

The response will be an account.authorizationForm constructor, with info about the required document types, the URL of the service's privacy policy, as well as info about the bot to which the form should be sent.
If the form was already submitted at least once, the constructor will also contain a list of already submitted data, along with eventual errors.

The user should accept the privacy policy and proceed to fill in the required data, and the client should encrypt and upload it as described in the Encryption article ».

#### Submitting the passport form

Once the user finishes uploading the required documents and clicks on the submit button, the client calls account.acceptAuthorization, submitting the documents to the bot associated to the service.

- As before, bot_id, scope and public_key are taken from the authorization request URI.

- value_hashes is used by the server to choose which document of which type to send to the bot: the type field should be set to the document type, and the hash field should be set to the data_hash/file_hash generated when uploading encrypting the data ».

- credentials contains the encrypted credentials required by the service to decrypt the sent E2E encrypted secure values: it is generated as described in Passport Credentials ».

Finally, the client opens the callback URL (if present).

#### Handling invalid forms

If any of the values of the submitted form are rejected by the service, the bot calls the appropriate method to set information about errors.

The user can find out about these errors directly from the service, or, if they decide to restart the process and resend the corrected data, directly from the authorization form (errors field).

