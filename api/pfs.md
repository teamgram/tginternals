# Perfect Forward Secrecy

##### Related articles



Perfect Forward Secrecy in Secret Chats
Security guidelines for developers



> This article is about Perfect Forward Secrecy in cloud chats, see also PFS in Secret Chats.

---

Telegram supports Perfect Forward Secrecy (PFS).

To make this possible, the client generates a permanent authorization key using p_q_inner_data and a temporary key using p_q_inner_data_temp. (See Creating an Authorization Key for more info.) These 2 operations may be done in parallel using different connections. The client must save an expires_at unix timestamp expires_at = time + expires_in.

Important: in order to achieve PFS, the client must never use the permanent auth_key_id directly. Every message that is sent to MTProto, must be encrypted by a temp_auth_key_id, that was bound to the perm_auth_key_id.

An unbound temp_auth_key_id may only be used with the following methods:

- auth.bindTempAuthKey

- help.getConfig

- help.getNearestDc

In order to bind a temporary authorization key to the permanent key the client creates a special binding message and executes the auth.bindTempAuthKey method using temp_auth_key. Once auth.bindTempAuthKey has been executed successfully, the client may continue using the API as usual; the client must also rewrite client info using initConnection after each binding. Each permanent key may only be bound to one temporary key at a time, binding a new temporary key overwrites the previous one.

Once the temporary key expires, the client needs to generate a new temporary key using p_q_inner_data_temp. Then it needs to re-bind that new temporary key to the initial permanent key. A new key can also be generated in advance, so that the client has a new key ready by the time the old one has expired.

For additional security, the client can store the temporary authorization key in RAM only and never save it in persistent storage.

A temporary authorization key may expire at any moment before expires_at, since such keys are also stored only in the RAM on the server-side. Be prepared to handle resulting MTProto errors correctly (non-existent auth_key_id results in a 404 error).

