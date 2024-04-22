# Telegram Passport Manual
Telegram Passport is a unified authorization method for services that require personal identification. Users can upload their documents once, then instantly share their data with services that require real-world ID (finance, ICOs, etc.). Telegram doesn't have access to the users' personal information thanks to end-to-end encryption.
### Overview
From the perspective of a service that requires real-world ID, the process looks like this:
- A user presses "Log in with Telegram" on your website or in your app.
- You request the data you need.
- The user accepts your privacy policy and agrees to share their data.
- The user's Telegram app downloads and decrypts the data you requested from the end-to-end encrypted storage on Telegram.
- If some of the data you requested is missing, the user can add it to their Telegram Passport at this point.
- The user's app encrypts the data with your public key and sends it to you.
- You decrypt the data, check it for errors and re-request any missing or invalid information.
- You sign the user up for your service. Tada!
Check out this example to see Telegram Passport in action.
> To learn more about Telegram Passport from the perspective of a user, please see this blog post and the technical MTProto documentation.
See this page if you're interested in encryption algorithms used on Telegram's side.
### Recent changes
#### August 25, 2018
Telegram Passport 1.1 (blog post)
- Added support for requesting several documents of one type. See the new objects PassportScope, PassportScopeElement, PassportScopeElementOneOfSeveral and PassportScopeElementOne.
- Added support for middle names.
- Added support for requesting certified English translations for documents (see Fields; new field translation also added to the SecureValue object). Note: Please only request translations after you have received a valid document that requires one.
- Added support for requesting names in the language of the user's country of residence (if other than English). New fields first_name_native, last_name_native and middle_name_native added to the PersonalDetails object.
- Replaced the payload parameter with the new parameter nonce, which serves the same function, to make the purpose more obvious (see Request Parameters and the Credentials object).
- Updated the example page to support the new functionality.
### Setting Up Telegram Passport
To integrate Telegram Passport into your login or verification flow, you need a working Telegram bot (see this page for information on how to get one).
To request data from Telegram Passport users, your bot will need to generate a pair of encryption keys.
#### Generating a private key
First, use a console to generate a private key:
WARNING: Keep your private key SECRET!
#### Generating your public key
Then use the console to print the corresponding public key:
Use the /setpublickey command with @BotFather to connect this public key with your bot.
#### Privacy Policy
Add a link to your Privacy Policy by using the /setprivacypolicy command. Users will see this link when offered to authorize you to access their data.
### Requesting Information
#### SDK
To request information stored in a Telegram Passport, use one of these SDKs:
- iOS/macOS SDK
- Android SDK
- Javascript SDK
#### Request Parameters
Use the following parameters to request information with the SDK:
#### PassportScope
This object represents the data to be requested.
#### PassportScopeElement
This object represents a requested element, should be one of:
- PassportScopeElementOneOfSeveral - use to request any one of the documents included in the scope.
- PassportScopeElementOne – use to request one particular document.
#### PassportScopeElementOneOfSeveral
This object represents several elements one of which must be provided.
#### PassportScopeElementOne
This object represents one particular element that must be provided. If no options are needed, String can be used instead of this object to specify the type of the element.
You can also use the special type "id_document" as an alias for one of "passport", "driver_license", "identity_card" and the special type "address_document" as an alias for one of "utility_bill", "bank_statement", "rental_agreement". 
So {"type":"id_document",selfie:true} is equal to {"one_of":["passport","driver_license","identity_card"],selfie:true}.
#### Fields
Your bot can request personal details, one or several types of identity document, residential address, one or several types of proof of address document, a phone number, or an email address. You can also request optional selfies with the document and certified English translations of the document.
This is just a list of data types that can be requested, and the encrypted objects that will contain such data.
> Note: We suggest to only request English translations after you have received a valid document that requires one.
#### PersonalDetails
This object represents personal details.
#### ResidentialAddress
This object represents a residential address.
#### IdDocumentData
This object represents the data of an identity document.
#### PassportFile
This object represents a PassportFile related to a document. The file is up to 10 MB in size and in the .jpg format.
### Receiving information
When the user confirms your request by pressing the "Authorize" button, the Bot API sends an Update with the field passport_data to the bot that contains encrypted Telegram Passport data.
> Note that all base64-encoded fields should be decoded before use.
#### Decrypting data
To decrypt the received data, first, decrypt the credentials contained in EncryptedCredentials.
> Note that all hashes represent as raw binary data, not hexits
#### Credentials
Credentials is a JSON-serialized object.
IMPORTANT: Make sure that the nonce is the same as was passed in the request.
#### SecureData
This object represents the credentials required to decrypt encrypted data. All fields are optional and depend on fields that were requested.
#### SecureValue
This object represents the credentials required to decrypt encrypted values. All fields are optional and depend on the type of fields that were requested.
#### DataCredentials
These credentials can be used to decrypt encrypted data from the data field in EncryptedPassportElement.
#### FileCredentials
These credentials can be used to decrypt encrypted files from the front_side, reverse_side, selfie, files and translation fields in EncryptedPassportElement.
### Fixing errors
If the data you received contains errors, the bot can use the setPassportDataErrors method to inform the user and request information again. The user will not be able to resend the data, until all errors are fixed.
