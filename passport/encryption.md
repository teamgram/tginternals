# Telegram Passport Encryption Details
Telegram Passport data is stored encrypted End-to-End which means that the Telegram server does not have access to the data and only functions as a storage for encrypted data it can't decipher. Encryption and decryption are handled exclusively by the Telegram clients, which are open source.
### Overview
To encrypt each particular element of Telegram Passport, the client generates a random secret. The secret is a 32-byte number with the modulo 255 sum of bytes equal to 239. This secret is in turn encrypted with the passport_secret that is generated when the user creates their Telegram Passport. passport_secret is encrypted with the user's password and is stored encrypted in the Telegram Cloud.
### Passport Secret
The passport secret is one of the secret parameters used to encrypt the data uploaded by the user to the Telegram Cloud.
When first setting up Telegram Passport it must be created, encrypted and uploaded as described in Passport Secret Encryption.
When using Telegram Passport normally, it must be downloaded and decrypted for use as described in Passport Secret Decryption.
The passport secret must also be downloaded, re-encrypted and re-uploaded as described in Passport Secret Encryption if a new, more secure encryption algorithm is defined in a newer version of Telegram or the 2FA password is updated.
#### Passport Secret Encryption
First of all, server-side passport parameters are fetched, schema:
When Telegram Passport is first used, the client generates a passport_secret (a 32-byte number with the modulo 255 sum of bytes equal to 239), using a part of server-generated random secure_random from account.password as an additional source of entropy for OpenSSL (when re-encrypting the passport_secret with a more secure algorithm or after a 2FA password change, the previous passport_secret is used, instead). 
Then passport_secret is then encrypted using the user's password and hashed using the schema and parameters specified in the new_algo field of account.password.
The server should always return a securePasswordKdfAlgoPBKDF2HMACSHA512iter100000 constructor in the new_algo field.
If securePasswordKdfAlgoUnknown is returned, the remotely stored secret is encrypted using a new algorithm, not supported by the current client: the user should update their app.
The other constructors may be used only when decrypting old passport parameters generated by a legacy client; in this case, the passport secret should be re-encrypted and updated using new_algo.
- First of all, a fingerprint of the secret is calculated ( passport_secret_fingerprint ):
- passport_secret_fingerprint = long( slice( SHA256( passport_secret ), 0, 8 ) )
- Next the user's 2FA plaintext password is hashed using the specified algorithm.
- securePasswordKdfAlgoPBKDF2HMACSHA512iter100000
- The following parameters are extracted/generated:
- 8 bytes of the server salt server_passport_salt from the salt field of securePasswordKdfAlgoPBKDF2HMACSHA512iter100000 constructor
- 32 random bytes of the client salt client_passport_salt.
- To make the password hashes stored on the server more resilient to brute-force attacks while maintaining practical speeds on the range of devices popular among Telegram users, PBKDF2-HMAC-SHA512 with 100000 iterations is used:
- server_passport_salt = new_algo.salt
- client_passport_salt = random_bytes(32)
- passport_secret_salt = server_passport_salt + client_passport_salt
- password_hash = PBKDF2( password, passport_secret_salt, HMACSHA512, 100000)
- The secret_key and iv parameters are extracted from the generated password_hash
- secret_key = slice( password_hash, 0, 32 )
- iv = slice( password_hash, 32, 16 )
- The passport_secret generated previously is encrypted using AES256-CBC with the key secret_key and iv:
- encrypted_passport_secret = AES256_CBC_ENC(passport_secret, secret_key, iv)
- The encrypted_passport_secret is stored on the server together with the passport_secret_salt and the fingerprint of the secret passport_secret_fingerprint:
- Schema:
- boolFalse#bc799737 = Bool;
- boolTrue#997275b5 = Bool;
- inputCheckPasswordSRP#d27ff082 srp_id:long A:bytes M1:bytes = InputCheckPasswordSRP;
- securePasswordKdfAlgoPBKDF2HMACSHA512iter100000#bbf2dda0 salt:bytes = SecurePasswordKdfAlgo;
- secureSecretSettings#1527bcac secure_algo:SecurePasswordKdfAlgo secure_secret:bytes secure_secret_id:long = SecureSecretSettings;
- account.passwordInputSettings#c23727c9 flags:# new_algo:flags.0?PasswordKdfAlgo new_password_hash:flags.0?bytes hint:flags.0?string email:flags.1?string new_secure_settings:flags.2?SecureSecretSettings = account.PasswordInputSettings;
- ---functions---
- account.updatePasswordSettings#a59b102f password:InputCheckPasswordSRP new_settings:account.PasswordInputSettings = Bool;
- The client calls account.updatePasswordSettings.
- The password parameter is generated using the user's 2FA password as per updating the 2FA password.
- The account.passwordInputSettings constructor in new_settings should contain only the new_secure_setting parameter with the secureSecretSettings.
- The secureSecretSettings constructor is generated thusly:
- secure_algo is set to the new_algo field of account.password, used to generate the encrypted passport secret: salt is substituted with passport_secret_salt
- secure_secret is set to the new encrypted_passport_secret
- secure_secret_id is set to the new passport_secret_fingerprint
Subsequently, the client receives the encrypted passport_secret from the server and decrypts it after the user enters their password ».
In case the password is changed or a more secure algorithm is introduced in an update of the API, the client re-encrypts the passport_secret using the new password. 
If the password is disabled, all Telegram Passport data is lost.
#### Passport Secret Decryption
Schema:
The client requests the user's 2FA password and generates the SRP paramaters to be passed to account.getPasswordSettings.
If the password is correct, an account.passwordSettings constructor with secureSecretSettings is returned.
encrypted_passport_secret, passport_secret_fingerprint parameters are extracted from the secureSecretSettings constructor:
The combined passport_secret_salt is extracted from the SecurePasswordKdfAlgo.
Similar to passport secret encryption, the following process is used to decrypt and verify the encrypted_passport_secret:
- The user's 2FA plaintext password is hashed using the specified algorithm.
- securePasswordKdfAlgoPBKDF2HMACSHA512iter100000
- To make the password hashes stored on the server more resilient to brute-force attacks while maintaining practical speeds on the range of devices popular among Telegram users, PBKDF2-HMAC-SHA512 with 100000 iterations is used:
- password_hash = PBKDF2( password, passport_secret_salt, HMACSHA512, 100000)
- securePasswordKdfAlgoSHA512
- This mode can only be found in hashes generated by legacy clients: hashes generated with this mode must be re-encrypted and updated using securePasswordKdfAlgoPBKDF2HMACSHA512iter100000 as described in Passport Secret Encryption.
- password_hash = SHA512( passport_secret_salt + password + passport_secret_salt )
- The secret_key and iv parameters are extracted from the generated password_hash
- secret_key = slice( password_hash, 0, 32 )
- iv = slice( password_hash, 32, 16 )
- The encrypted_passport_secret is decrypted using AES256-CBC with the key secret_key and iv:
- passport_secret = AES256_CBC_DEC(encrypted_passport_secret, secret_key, iv)
- The passport_secret is verified by generating and checking the fingerprint:
- my_passport_secret_fingerprint = long( slice( SHA256( passport_secret ), 0, 8 ) )
- The client must verify that passport_secret_fingerprint is indeed equal to my_passport_secret_fingerprint.
The passport_secret can now be used to decrypt encrypted passport data stored on telegram servers:
### Data and File Encryption
#### Encryption
To encrypt Telegram Passport data, the client generates a data_secret (a 32-byte number with the modulo 255 sum of bytes equal to 239). The data is encrypted according to the following scheme:
- Data is padded to a length that is divisible by 16 bytes. To achieve this, 32 to 255 bytes are added at the beginning, where the first byte always holds the number of added bytes and the rest are random.
- We calculate the hash from this data data_hash:
- data_hash = SHA256( data_bytes )
- The encryption key data_key is calculated:
- data_secret_hash = SHA512( data_secret + data_hash )
- data_key = slice( data_secret_hash, 0, 32 )
- iv = slice( data_secret_hash, 32, 16 )
- Data is encrypted using AES256-CBC with the key data_key and iv:
- encrypted_data = AES256_CBC_ENC(data, data_key, iv)
- secret_key, the key for encrypting the data_secret, is calculated:
- secret_hash = SHA512( passport_secret + data_hash )
- secret_key = slice( secret_hash, 0, 32 )
- iv = slice( secret_hash, 32, 16 )
- data_secret is encrypted using AES256-CBC with the key secret_key and iv:
- encrypted_data_secret = AES256_CBC_ENC(data_secret, secret_key, iv)
- encrypted_data together with the encrypted_data_secret and data_hash are saved on the server:
- Schema:
- inputSecureFileUploaded#3334b0f0 id:long parts:int md5_checksum:string file_hash:bytes secret:bytes = InputSecureFile;
- inputSecureFile#5367e5be id:long access_hash:long = InputSecureFile;
- secureValueTypePersonalDetails#9d2a81e3 = SecureValueType;
- secureValueTypePassport#3dac6a00 = SecureValueType;
- secureValueTypeDriverLicense#6e425c4 = SecureValueType;
- secureValueTypeIdentityCard#a0d0744b = SecureValueType;
- secureValueTypeInternalPassport#99a48f23 = SecureValueType;
- secureValueTypeAddress#cbe31e26 = SecureValueType;
- secureValueTypeUtilityBill#fc36954e = SecureValueType;
- secureValueTypeBankStatement#89137c0d = SecureValueType;
- secureValueTypeRentalAgreement#8b883488 = SecureValueType;
- secureValueTypePassportRegistration#99e3806a = SecureValueType;
- secureValueTypeTemporaryRegistration#ea02ec33 = SecureValueType;
- secureValueTypePhone#b320aadb = SecureValueType;
- secureValueTypeEmail#8e3ca7ee = SecureValueType;
- securePlainPhone#7d6099dd phone:string = SecurePlainData;
- securePlainEmail#21ec5a5f email:string = SecurePlainData;
- secureData#8aeabec3 data:bytes data_hash:bytes secret:bytes = SecureData;
- inputSecureValue#db21d0a7 flags:# type:SecureValueType data:flags.0?SecureData front_side:flags.1?InputSecureFile reverse_side:flags.2?InputSecureFile selfie:flags.3?InputSecureFile translation:flags.6?Vector<InputSecureFile> files:flags.4?Vector<InputSecureFile> plain_data:flags.5?SecurePlainData = InputSecureValue;
- ---functions---
- account.saveSecureValue#899fe31d value:InputSecureValue secure_secret_id:long = SecureValue;
- account.saveSecureValue must be used to save an encrypted passport value of a certain type.
- The secure_secret_id parameter must be set to the passport_secret_fingerprint of the passport_secret used to encrypt the data_secret.
- The inputSecureValue constructor contains info about passport data of a certain type, identified by the chosen SecureValueType constructor.
- Depending on the chosen type, encrypted data will have to be stored into a secureData constructor, uploaded as an InputSecureFile, or in the case of email addresses and phone numbers, verified and provided in a SecurePlainData constructor.
- For more info on each mode, and when each one should be used, read on.
#### Packing
##### SecureData
- data is an encrypted and padded (see Encryption) JSON-serialized object of one of the following types: PersonalDetails, IdDocumentData, ResidentialAddress, depending on the chosen type.
- Data must be in JSON format and not TL, as it has to be passed directly to the service using E2E encryption, without the bot API middleman to convert TL objects.
- data_hash is the data_hash
- secret is the encrypted_data_secret
Data is an encrypted and padded JSON-serialized object of one of the specified JSON types, depending on the chosen type.
##### InputSecureFile
Files (JPG format, max. 10 MB) are encrypted and padded (see Encryption), and then uploaded chunk by chunk as described in files », except that instead of generating an inputFile, an inputSecureFile should be generated, instead.
- As for secret chat files, the md5_checksum is to be set to the MD5 hash of the encrypted file, for a server-side integrity check.
- The file_hash field should be set to the data_hash of the data.
- The secret field is the encrypted_data_secret.
##### SecurePlainData
The email/phone is passed in plaintext using the respective SecurePlainData constructor.
To verify a phone number or email and use it in Telegram Passport, use the appropriate methods:
- account.sendVerifyEmailCode - Send the verification email code for telegram passport.
- account.verifyEmail - Verify an email address for telegram passport.
- account.sendVerifyPhoneCode - Send the verification phone code for telegram passport.
- account.verifyPhone - Verify a phone number for telegram passport.
- auth.resendCode - Only for phone code verification, resend the code using a different method
- auth.cancelCode - Only for phone code verification, cancel phone code verification
The flow is similar to the one used for logging in:
- Send email/phone code using the appropriate account.sendVerify*Code method
- Make sure to pass emailVerifyPurposePassport as verification purpose to account.sendVerifyEmailCode.
- Pass the received code to the appropriate account.verify* method
- Only for phone code verification, you can also resend/cancel the phone code using auth.resendCode/auth.cancelCode, as for logging in.
For more info, see the authorization docs.
#### When to use each constructor.
The schema for the inputSecureValue constructor defines the constructor to use for each field.
Here's a list of possible SecureValueTypes, and the parameters that can be set/requested when using each type.
#### Fetching and deleting stored passport data
The above methods can be used to fetch or remove encrypted Telegram Passport files stored in the Telegram Cloud by document type.
### Passport Credentials
When a service requests data, it passes a nonce to the client. The nonce is a cryptographically secure unique identifier which allows the service to identify a request when receiving data as well as confirm the integrity of the data. The Telegram server doesn't have access to this nonce.
Once the user authorizes the Telegram Passport data transfer, the client forms the credentials (Credentials JSON object). Credentials contain the data_hash and data_secret from each element of Telegram Passport to which the user has allowed access. In addition to this, the credentials will always contain the nonce that the client received from the service at the initiation of the request.
Credentials are then passed to the service through the Bot API in encrypted form. To encrypt the credentials, the client generates a credentials_secret (a 32-byte number with the modulo 255 sum of bytes equal to 239). Then the credentials are encrypted according to the following scheme:
- Credentials are padded to a length which is divisible by 16 bytes. To achieve this, 32 to 255 bytes are added at the beginning, where the first byte always holds the number of added bytes and the rest are random.
- A hash of the padded credentials credentials_hash is calculated:
- credentials_hash = SHA256( credentials )
- The encryption key credentials_key is calculated:
- credentials_secret_hash = SHA512( credentials_secret + credentials_hash )
- credentials_key = slice( credentials_secret_hash, 0, 32 )
- iv = slice( credentials_secret_hash, 32, 16 )
- Credentials are encrypted using AES256-CBC with the key credentials_key and iv.
- encrypted_credentials = AES256-CBC-ENC(credentials, credentials_key, iv)
- credentials_secret is encrypted with the public RSA-key of the service with OPENSSL_PKCS1_OAEP_PADDING.
- encrypted_credentials_secret = RSA-ENC(credentials_secret, key, OPENSSL_PKCS1_OAEP_PADDING)
- The encrypted credentials are passed to the service via the MTProto API together with the encrypred credentials_secret and credentials_hash. Along with the credentials, the service receives from the Telegram Cloud the data it requested in encrypted form. See Submitting the Passport Form and PassportData:
- secureCredentialsEncrypted#33f0ea47 data:bytes hash:bytes secret:bytes = SecureCredentialsEncrypted;
- data is the encrypted_credentials
- hash is the credentials_hash
- secret is the encrypted_credentials_secret
Then the service decrypts the data as described here.