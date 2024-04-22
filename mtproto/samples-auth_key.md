# Auth key generation example
In the examples below, the transport headers are omitted:
> For example, for the abridged version of the transport », the client sends 0xef as the first byte (important: only prior to the very first data packet), then the packet length is encoded with a single byte (0x01-0x7e = data length divided by 4; or 0x7f followed by 3 bytes (little endian) divided by 4) followed by the data itself. In this case, server responses have the same structure (although the server does not send 0xefas the first byte).
Detailed documentation on creating authorization keys is available here ».
#### DH exchange initiation
##### 1) Client sends query to server
Sent payload (excluding transport headers/trailers):
Payload (de)serialization:
##### 2) Server sends response of the form
Received payload (excluding transport headers/trailers):
Payload (de)serialization:
In our case, the client only has the following public keys, with the following fingerprints:
- 85FD64DE851D9DD0
Let's choose the only matching key, the one with fingerprint equal to 85FD64DE851D9DD0.
#### Proof of work
##### 3) Client decomposes pq into prime factors such that p < q.
Decompose into 2 prime cofactors p < q: 2453830868973477031 = 1343866633 * 1825948207
#### Presenting proof of work; Server authentication
##### 4) encrypted_data payload generation
First of all, generate an encrypted_data payload as follows:
Generated payload (excluding transport headers/trailers):
Payload (de)serialization:
The serialization of P_Q_inner_data produces data, which is used to generate encrypted_data as specified in step 4.1.
These are the inputs to the algorithm specified in step 4.1:
And this is the output:
The length of the final string is 256 bytes.
##### 5) Send req_DH_params query with generated encrypted_data
Sent payload (excluding transport headers/trailers):
Payload (de)serialization:
##### 6) Server responds with:
Received payload (excluding transport headers/trailers):
Payload (de)serialization:
Decrypt encrypted_answer using the reverse of the process specified in step 6:
Yielding:
Generated payload (excluding transport headers/trailers):
Payload (de)serialization:
##### 7) Client computes random 2048-bit number b (using a sufficient amount of entropy) and sends the server a message
First, generate a secure random 2048-bit number b:
Then compute g_b = pow(g, b) mod dh_prime
###### 7.1) generation of encrypted_data
Generated payload (excluding transport headers/trailers):
Payload (de)serialization:
The serialization of Client_DH_Inner_Data produces a string data. This is used to generate encrypted_data as specified in step 6, using the following inputs:
Process:
Output:
The length of the final string is 336 bytes.
###### 7.2) set_client_DH_params query
Sent payload (excluding transport headers/trailers):
Payload (de)serialization:
##### 8) Auth key generation
The client computes the auth_key using formula g_a^b mod dh_prime:
##### 9) Final server reply
The server verifies and confirms that auth_key_hash is unique: since it's unique, it replies with the following:
Received payload (excluding transport headers/trailers):
Payload (de)serialization:
