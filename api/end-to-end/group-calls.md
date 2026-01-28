# E2E Group Calls

This article describes the end-to-end encryption used for Telegram group voice and video calls, incorporating a blockchain for state management and enhanced security.

##### Related Articles



End-to-End Encryption in Secret Chats
Security Guidelines for Client Developers
TL Language



---

### Overview

Telegram end-to-end encrypted group calls generally rely on 3 components to manage communication securely among multiple participants:

This document details the technical implementation of these components.

### High-Level Workflow

Below follows a high-level workflow for working with group calls. As mentioned, the blockchain underpins the core operations of joining, leaving, and maintaining a consistent state within a group call.

#### Joining a Call

#### Removing a Participant

> Note: Self-removal is not supported via this mechanism, as a participant cannot create a block that removes themselves while simultaneously generating a new key for the others.

#### Security Considerations

- Clients must only apply blocks received from the server, even those they proposed themselves. The server enforces block ordering and prevents forks.

- All participants must verify that they see the same verification emojis, which are derived from the blockchain state using the commit-reveal protocol detailed later.

- If the server were to deliver different valid blocks to different participants (a fork), their blockchain hashes, and consequently their verification emojis, would permanently diverge. The reliance on the server prevents this under normal operation.

---

### Blockchain State Management

A dedicated blockchain provides a distributed, verifiable, and synchronized history of the group call's state.

#### Block Structure

Blocks form the chain, linking sequentially to maintain history. The structure is defined as follows (based on e2e_api.tl):

```
e2e.chain.block flags:# signature:int512 prev_block_hash:int256 changes:vector<e2e.chain.Change> height:int state_proof:e2e.chain.StateProof signature_public_key:flags.0?int256 = e2e.chain.Block;
```

Namely:

- signature: A cryptographic signature verifying the block's authenticity.

- prev_block_hash: The SHA256 hash of the preceding block, forming the chain link.

- changes: A list of state modifications applied by this block.

- height: The sequential number of the block in the chain.

- state_proof: Cryptographic proof (including group state hash, shared key info hash) representing the blockchain state after this block is applied.

- signature_public_key: The public key of the participant who created and signed the block.

#### Blockchain State

```
e2e.chain.stateProof flags:# kv_hash:int256 group_state:flags.0?e2e.chain.GroupState shared_key:flags.1?e2e.chain.SharedKey = e2e.chain.StateProof;
```

Blockchain states consist of:

#### Signature and Hash Generation

- Signature: Calculated over the TL-serialized block with the signature field itself zeroed out. The specific serialization format follows standard TL rules.

- Block Hash: The SHA256 hash of the complete TL-serialized block.

#### Change Types for Group Calls

Blocks contain changes that modify the blockchain state. The types used in group calls are:

#### Participants and Permissions

Participants are defined by their user_id, public_key, and associated permissions within the GroupState:

```
e2e.chain.groupParticipant user_id:long public_key:int256 flags:# add_users:flags.0?true remove_users:flags.1?true version:int = e2e.chain.GroupParticipant;
```

- add_users: Permission to add new participants.

- remove_users: Permission to remove existing participants.

> Note: For improved user experience, any person can currently join a call with server permission, without requiring explicit confirmation from existing participants. While the blockchain supports an explicit confirmation mode, we currently use external_permissions in the blockchain state to allow self-addition to groups.

#### Block Application Process

Blocks must be applied atomically (all changes succeed or none do) and sequentially. The validation process is as follows:

The blockchain starts with a conceptual "genesis" block at height: -1 with a hash of UInt256(0) and effective self_join_permissions allowing the very first participant action.

> Note: For optimization purposes, the signature_public_key can be omitted if it matches the first participant's key in the group state. Similarly, state proof components (group_state, shared_key) can sometimes be omitted if corresponding Set* changes are present in the block.

#### Applying Specific Changes

- Participant Management (ChangeSetGroupState):

- Requires the add_users permission to add participants. Added users receive permissions that are a non-strict subset of the creator's permissions (with an exception allowing granting permissions to others).

- Requires the remove_users permission to remove participants.

- Participant user_id and public_key must be unique.

- This change always clears the existing shared key state. A new key must be set in a subsequent block if needed.

- Shared Key Updates (ChangeSetSharedKey):

- Can only be initiated by an existing participant.

- Cannot overwrite an existing key directly; requires a ChangeSetGroupState (which clears the key) first, followed by a new ChangeSetSharedKey in a subsequent block.

- The dest_user_id list in the SharedKey structure must exactly match the current list of participants in the group state.

- The block creator must be included as a participant when setting a new key.

> Note: Participants cannot remove themselves via ChangeSetGroupState, as this would require generating a new shared key for the remaining members, which they couldn't do after removal. Active participants should remove inactive ones.

##### Implementation Notes

- Serialization: Blocks and their contents are serialized using the standard Telegram TL serialization methods before signing or hashing.

- Concurrency: If multiple valid blocks for the same height are created concurrently, only the first one to be successfully applied will be appended. Subsequent blocks for that height will be rejected by participants due to the height mismatch, preventing forks and ensuring a linear history.

- Validation: Clients must only apply blocks received from the server (even blocks they created themselves). The server performs validation and ordering to prevent forks and ensure consistency. Clients should retry sending created blocks/broadcasts until acknowledged (success or error) by the server.

---

### Encryption Protocol

The following protocol encrypts call data (audio/video frames) and manages shared keys securely.

#### Core Primitives

The encryption relies on the following primitive functions, similar to MTProto 2.0. Note that KDF refers to HMAC-SHA512 throughout this document.

- encrypt_data(payload, secret, extra_data)

> Encrypts payload using a secret. extra_data will be used as part of MAC. large_msg_id will be used later to sign the packet.

```
padding_size = 16 + 15 - (payload.size + 15) % 16
padding = random_bytes(padding_size)
padding[0] = padding_size
padded_data = padding || payload
large_secret = KDF(secret, "tde2e_encrypt_data")
encrypt_secret = large_secret[0:32]
hmac_secret = large_secret[32:64]
large_msg_id = HMAC-SHA256(hmac_secret, padded_data || extra_data || len(extra_data))
msg_id = large_msg_id[0:16]
(aes_key, aes_iv) = HMAC-SHA512(encrypt_secret, msg_id)[0:48]
encrypted = aes_cbc(aes_key, aes_iv, padded_data)
Result: (msg_id || encrypted), large_msg_id
```

- encrypt_header(header, encrypted_msg, secret)

> Encrypts a 32-byte header using context from encrypted_msg and a secret.

```
msg_id = encrypted_msg[0:16]
encrypt_secret = KDF(secret, "tde2e_encrypt_header")[0:32]
(aes_key, aes_iv) = HMAC-SHA512(encrypt_secret, msg_id)[0:48]
encrypted_header = aes_cbc(aes_key, aes_iv, header)
```

Security:

- Decryption routines must re-calculate and verify the msg_id before processing the decrypted payload.

- Replay protection is managed at the packet level using seqno.

#### Packet Encryption

Audio and video data packets are encrypted using the following process:

- encrypt_packet(payload, extra_data, active_epochs, user_id, channel_id, seqno, private_key)

> Encrypts payload for transmission, associating it with active blockchain epochs. Epochs are essentially blocks whose shared keys are currently used for encryption.

magic1 is magic for e2e.callPacket = e2e.CallPacket;
magic2 is magic for e2e.callPacketLargeMsgId = e2e.CallPacketLargeMsgId;

#### Security Considerations

- Replay Protection: The seqno must be unique and monotonically increasing for each (public key, channel_id) pair. In case of overflow, the client must leave the call. Receivers must track recently received seqno values and discard packets with old or duplicate numbers.

- Signature Verification: During decryption, the receiver must use the user_id (provided out-of-band) to look up the sender's public_key in the relevant blockchain state (epoch specified in header_a). This public key is used to verify the signature within the decrypted signed_payload.

- Unique private keys: Clients must use unique private keys each time they add themselves to the blockchain. Otherwise, replay attacks could be possible.

#### Shared Key Encryption

When a ChangeSetSharedKey operation occurs in the blockchain, the new shared key material is distributed securely as follows:

#### Security Considerations

- Decryption is not guaranteed for all participants (e.g., if a participant has an outdated app or corrupted state).

- However, all participants who can successfully decrypt the key material (by reversing the encrypt_header and encrypt_data steps using their private key and the ephemeral public key) will arrive at the identical group_shared_key.

- Participants unable to decrypt the key must exit the call immediately, and specifically must not participate in the emoji generation process.

---

### Key Verification and Emoji Generation

To ensure participants are communicating securely without a Man-in-the-Middle (MitM) attack, and to prevent manipulation of verification codes, a commit-reveal protocol is used to generate emojis based on the blockchain state and shared randomness.

#### Commit-Reveal Protocol Workflow

#### TL Schema for Broadcasts

```
// Phase 1: Commit
e2e.chain.groupBroadcastNonceCommit signature:int512 public_key:int256 chain_height:int32 chain_hash:int256 nonce_hash:int256 = e2e.chain.GroupBroadcast;

// Phase 2: Reveal
e2e.chain.groupBroadcastNonceReveal signature:int512 public_key:int256 chain_height:int32 chain_hash:int256 nonce:int256 = e2e.chain.GroupBroadcast;
```

The signature in both cases covers the TL-serialized object with the signature field itself zeroed out.

#### Security Considerations

- The final emoji_hash is unpredictable to any single participant before the reveal phase, as it depends on random nonces from all others.

- Participants should only process broadcast messages (commits/reveals) received from the server. Emojis should only be displayed once the process completes successfully for all participants (within reasonable network latency).

- The two-phase protocol prevents any participant (even one controlling block creation) from selectively revealing their nonce or trying multiple nonces to influence the final emoji outcome based on others' revealed values.

---

### Full TL Schema

```
e2e.chain.groupBroadcastNonceCommit#d1512ae7 signature:int512 user_id:int64 chain_height:int32 chain_hash:int256 nonce_hash:int256 = e2e.chain.GroupBroadcast;
e2e.chain.groupBroadcastNonceReveal#83f4f9d8 signature:int512 user_id:int64 chain_height:int32 chain_hash:int256 nonce:int256 = e2e.chain.GroupBroadcast;

e2e.chain.groupParticipant user_id:long public_key:int256 flags:# add_users:flags.0?true remove_users:flags.1?true version:int = e2e.chain.GroupParticipant;
e2e.chain.groupState participants:vector<e2e.chain.GroupParticipant> external_permissions:int = e2e.chain.GroupState;
e2e.chain.sharedKey ek:int256 encrypted_shared_key:string dest_user_id:vector<long> dest_header:vector<bytes> = e2e.chain.SharedKey;

e2e.chain.changeNoop nonce:int256 = e2e.chain.Change;
e2e.chain.changeSetValue key:bytes value:bytes = e2e.chain.Change;
e2e.chain.changeSetGroupState group_state:e2e.chain.GroupState = e2e.chain.Change;
e2e.chain.changeSetSharedKey shared_key:e2e.chain.SharedKey = e2e.chain.Change;

e2e.chain.stateProof flags:# kv_hash:int256 group_state:flags.0?e2e.chain.GroupState shared_key:flags.1?e2e.chain.SharedKey = e2e.chain.StateProof;

e2e.chain.block#639a3db6 signature:int512 flags:# prev_block_hash:int256 changes:vector<e2e.chain.Change> height:int state_proof:e2e.chain.StateProof signature_public_key:flags.0?int256 = e2e.chain.Block;

e2e.callPacket = e2e.CallPacket;
e2e.callPacketLargeMsgId = e2e.CallPacketLargeMsgId;
```

