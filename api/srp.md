# Two-factor authentication

Telegram uses the Secure Remote Password protocol version 6a to implement 2FA.

Example implementation: tdlib.

### Checking the password with SRP

To login to an account protected by a 2FA password or to perform some other actions (like changing channel owner), you will need to verify the user's knowledge of the current 2FA account password.

To do this, first the client needs to obtain SRP parameters and the KDF algorithm to use to check the validity of the password via account.getPassword method. For now, only the passwordKdfAlgoSHA256SHA256PBKDF2HMACSHA512iter100000SHA256ModPow algorithm is supported, so we'll only explain that.

Then, after the user provides a password, the client should generate an InputCheckPasswordSRP object using SRP and a specific KDF algorithm as shown below and pass it to appropriate method (e.g. auth.checkPassword in case of authorization).

This extension of the SRP protocol uses the password-based PBKDF2 with 100000 iterations using sha512 (PBKDF2HMACSHA512iter100000).
PBKDF2 is used to additionally rehash the x parameter, obtained using a method similar to the one described in RFC 2945 (H(s | H ( I | password | I) | s) instead of H(s | H ( I | ":" | password)) (see below).

Here, | denotes concatenation and + denotes the arithmetical operator +.
In all cases where concatenation of numbers passed to hashing functions is done, the numbers must be used in big-endian form, padded to 2048 bits; all math is modulo p.
Instead of I, salt1 will be used (see SRP protocol).
Instead of s, salt2 will be used (see SRP protocol).

The main hashing function H is sha256:

- H(data) := sha256(data)

The salting hashing function SH is defined as follows:

- SH(data, salt) := H(salt | data | salt)

The primary password hashing function is defined as follows:

- PH1(password, salt1, salt2) := SH(SH(password, salt1), salt2)

The secondary password hashing function is defined as follows:

- PH2(password, salt1, salt2) := SH(pbkdf2(sha512, PH1(password, salt1, salt2), salt1, 100000), salt2)

Client-side, the following parameters are extracted from the passwordKdfAlgoSHA256SHA256PBKDF2HMACSHA512iter100000SHA256ModPow object, contained in the account.password object.

- g := algo.g

- p := algo.p

- The client is expected to check whether p is a safe 2048-bit prime (meaning that both p and (p-1)/2 are prime, and that 2^2047 < p < 2^2048), and that g generates a cyclic subgroup of prime order (p-1)/2, i.e. is a quadratic residue mod p. Since g is always equal to 2, 3, 4, 5, 6 or 7, this is easily done using quadratic reciprocity law, yielding a simple condition on p mod 4g -- namely, p mod 8 = 7 for g = 2; p mod 3 = 2 for g = 3; no extra condition for g = 4; p mod 5 = 1 or 4 for g = 5; p mod 24 = 19 or 23 for g = 6; and p mod 7 = 3, 5 or 6 for g = 7. After g and p have been checked by the client, it makes sense to cache the result, so as to avoid repeating lengthy computations in future. This cache might be shared with one used for Authorization Key generation.

- If the client has an inadequate random number generator, it makes sense to use the secure_random of account.password as additional seed.

- password := (user-provided password)

- salt1 := algo.salt1

- salt2 := algo.salt2

- g_b := srp_B

- srp_B and srp_id are extracted from the account.password object.

The k parameter is generated, both on client and server:

- k := H(p | g)

The shared param u is generated: the client does this, and the server does the same with the g_a we will send him later (see below)

- u := H(g_a | g_b)

The final parameters are generated client-side only:

- x := PH2(password, salt1, salt2)

- v := pow(g, x) mod p

The server already has v, from when we set the password.

A final shared param is generated, for commodity:

- k_v := (k * v) mod p

Finally, the key exchange process starts on both parties.

The client computes a 2048-bit number a (using sufficient entropy or the server's random; see above) and generates:

- g_a := pow(g, a) mod p.

The server computes a 2048-bit number b using sufficient entropy and generates the g_b parameter that was sent to us (see above).

- g_b := (k_v + (pow(g, b) mod p)) mod p

Finally, the SRP session keys are generated:

Client side:

- t := (g_b - k_v) mod p (positive modulo, if the result is negative increment by p)

- s_a := pow(t, a + u * x) mod p

- k_a := H(s_a)

Server side:

- s_b := pow(g_a * (pow(v, u) mod p), b) mod p

- k_b := H(s_b)

Since:

- g_b := (k_v + (pow(g, b) mod p)) mod p

- t := (g_b - k_v) mod p

- t :=  ((k_v + (pow(g, b) mod p)) - k_v) mod p

- t := pow(g, b) mod p

- s_a := pow(t, a + u * x) mod p

- s_a := pow(pow(g, b) mod p, a + u * x) mod p

And:

- g_a := pow(g, a) mod p

- v := pow(g, x) mod p

- s_b := pow(g_a * (pow(v, u) mod p), b) mod p

- s_b := pow((pow(g, a) mod p) * (pow(pow(g, x) mod p, u) mod p), b) mod p

- s_b := pow(pow(g, a + x * u) mod p, b) mod p

- s_b := pow(pow(g, b) mod p, a + u * x) mod p

- s_a := pow(pow(g, b) mod p, a + u * x) mod p

This means:

- s_b === s_a

- k_b === k_a

Finally, as per SRP:

- M1 := H(H(p) xor H(g) | H(salt1) | H(salt2) | g_a | g_b | k_a)

M1 is passed to inputCheckPasswordSRP, along with g_a (as A parameter) and the srp_id, extracted from the account.password object.

The server then computes:

- M2 := H(H(p) xor H(g) | H(salt1) | H(salt2) | g_a | g_b | k_b)

Since we said that:

- s_b === s_a

- k_b === k_a

This means, if everything was done correctly,

- M1 === M2

If the password isn't correct, 400 PASSWORD_HASH_INVALID will be returned.

### Setting a new 2FA password

To set a new 2FA password use the account.updatePasswordSettings method.
If a password is already set, generate an InputCheckPasswordSRP object as per checking passwords with SRP, and insert it in the password field of the account.updatePasswordSettings method.
To remove the current password, pass an empty new_password_hash in the account.PasswordInputSettings object.

To set a new password, use the SRP parameters and the KDF algorithm obtained using account.getPassword when generating the password field.
Then generate a new new_password_hash using the KDF algorithm specified in the new_settings, just append 32 sufficiently random bytes to the salt1, first.
Proceed as for checking passwords with SRP, just stop at the generation of the v parameter, and use it as new_password_hash:

- v := pow(g, x) mod p

As usual in big endian form, padded to 2048 bits.

#### Email verification

When setting up two-factor authorization, it is recommended to set up a  recovery email, to allow recovery of the password through the user's email address, in case they forget it.

To set up a recovery email, it must first be verified.
This can be done directly when setting the new password using account.updatePasswordSettings by setting the email parameter and flag in the account.passwordInputSettings constructor.
If the email isn't verified, an EMAIL_UNCONFIRMED_X 400 error will be returned, where X is the length of the verification code that was just sent to the email.
Use account.confirmPasswordEmail to enter the received verification code and enable the recovery email.
Use account.resendPasswordEmail to resend the verification code.
Use account.cancelPasswordEmail to cancel the verification code.

To get the current recovery email, use account.getPasswordSettings.

### Password recovery

If the user has forgotten their 2FA password, the following recovery options are available:

- Logged-in sessions only: password reset »

- Logged-in and not logged-in sessions: email recovery »

- Not logged-in sessions: account deletion »

#### Password reset

Password reset can be requested from logged-in sessions only.

The following procedure can be used to reset the password without deleting the account:

If the user is already logged in and has forgotten their 2FA password, account.resetPassword can be used to initiate a password reset.
On success, the call will initially return a account.resetPasswordRequestedWait constructor and start a 7-day server-side timer, during which the user can abort the reset process using a button sent by the Telegram service account or directly in-UI using account.declinePasswordReset.

When the time comes, account.resetPassword is invoked once more, returning a account.resetPasswordOk to indicate that the password was successfully reset.

If the user recently requested a password reset that was canceled, account.resetPasswordFailedWait will be returned by the initial account.resetPassword call, and they must wait until the specified date before requesting another reset.

Note that if the user already knows their 2FA password and simply wants to disable 2FA, the same process used to enable the password must also be used to disable it ».

#### Email recovery

Email recovery can be requested from logged in sessions, and from non-logged in sessions if the user has successfully provided the login code.
In both cases, the account must have an associated recovery email ».

In order to recover a forgotten 2FA password, an email must be sent to the previously specified address using the auth.requestPasswordRecovery method.
Use auth.checkRecoveryPassword to make sure that the user provided a valid code.
Then use auth.recoverPassword with the received code to delete the current 2FA password, to set a new one follow these instructions ».

#### Account deletion

If the user has successfully provided the login code, but they forgot their 2FA password and they don't have access to any other logged-in session, the account can be deleted following these instructions ».

### Related pages

#### SRP design

