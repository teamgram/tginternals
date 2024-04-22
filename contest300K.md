# Telegram Cracking Contest Description

« Back to Contest Announcement

> The current round of the contest is over. Go to results »

In this contest you assume the role of a malicious entity in control of Telegram's servers. Your goal is to extract sensitive data (a secret email and password) from a conversation between two peers — Paul and Nick. They are represented by two virtual users that communicate via Secret Chats in Telegram.

Paul and Nick are both using clients that perform all the checks from Telegram Security Guidelines and compare their key visualizations over an independent channel as soon as a new Secret Chat is established. If any of these checks fails, they stop accepting messages in that Secret Chat. You control the entire process by sending commands to the Telegram user @CryptoContest, used as an interface for this contest. This enables contestants to try CPA, KPA, MITM and other kinds of active attacks and data tampering.

### Protocol

The protocol used by Paul and Nick to establish Secret Сhats and exchange messages is identical to the one used for Secret Chats in Telegram. Since we assume that the attacker is already in full control of the Telegram servers, basic MTProto encryption is bypassed altogether. In order to further simplify the task for contestants, we have removed irrelevant parameters, such as user_id and random_id.

The following TL scheme is used to establish Secret Chats in this contest:

For exchange of encrypted messages (see documentation), the up-to-date layer 17 scheme with sequence numbers is used, but with plain text message support only.

Each plaintext message is first created as a layer 17 decryptedMessage, then embedded in a decryptedMessageLayer and encrypted as explained in the Secret Chat documentation. For the purpose of this contest, it is the result of this encryption (ciphertext) that is exchanged between the parties.

Notice that sending messages in an actual Telegram Secret Chat involves further embedding of that ciphertext into an API call and an additional layer of MTProto encryption for client-server interaction. This step is omitted here, since we assume the attacker to be in control of the Telegram servers, not just of the communication lines between the clients and Telegram servers.

### Interface

To access the interface, find the Telegram user @CryptoContest using the Global Search by username in any of the Telegram apps. This is a special bot we created for this contest. You can control communication between Paul and Nick by sending particularly formed text messages to this bot and processing automatically generated answers to these messages (you may find the unofficial Linux CLI convenient for mass automated queries).

You can create as many parallel Secret Chats between Paul and Nick as you like using the bot — each of them will have a separate session_id. All data is represented in hexadecimal format, with the exception of the session_id.

### Commands

Below, A stands for the creator of the Secret Chat, B stands for the second party, S — the Telegram Server.

Each Secret Chat session in this contest is divided in two phases:

- Creating a Secret Chat

- Sending Encrypted Message

##### 1. Creating a Secret Chat

In order to create a new Secret Chat, six messages need to be exchanged:

To create a Secret Chat in this contest:

- Send the START command to the user @CryptoContest in Telegram. You'll get the getDhConfig query, sent by A to the Server, and the answer that the server would normally send to A. You shall also receive the new session_id as the first 32-bit integer. All further messages related to this particular session (Secret Chat instance) must be prefixed with this session_id in decimal form.

- After that, use the PASS command to pass the server's answer to A or ANSWER bytes to send a different answer instead. Bytes is represented by a string of an even number of hexadecimal digits. You'll receive the requestEncryption query as the result.

- After that, use the PASS command to pass this query to B or ANSWER bytes to arbitrarily change it. You‘ll receive B’s getDhConfig to the server as the result.

- As before, you can use either PASS or ANSWER bytes. You'll receive acceptEncryption as the result.

- As before, you can use either PASS or ANSWER bytes. You'll receive “Ok” as the result.

You will receive an error text as the result after any of these steps in case the participating clients perceive that something went wrong. This can happen if a security check is failed, or in the case that the first 128 bits of the SHA-1 of the newly created encryption key don‘t match on both parties’ clients when this stage is completed (this corresponds to Paul and Nick comparing the key visualizations for the Secret Chat in their Telegram apps).

If you obtain such an error, the session is failed and can no longer be used. You'll have to start new session. Note that the time to complete this phase is limited. Each step should not take longer than one hour, otherwise the Secret Chat will get cancelled.

Example:

##### 2. Sending Text Messages

Once the Secret Chat has been established, you can use the following queries to make Paul and Nick exchange text messages inside the Secret Chat:

- ASK [A|B] — asks A or B to send a random plaintext message to the other party. It is guaranteed that at least one of the first ten generated messages will contain the secret email and password that are the goal of this contest. It is also guaranteed that apart from that, all messages will contain only dictionary English words, spaces, line breaks and punctuation marks. The result to this query is the ciphertext corresponding to the randomly generated plaintext.

- TXT [A|B] bytes — asks A or B to encrypt bytes as the (plaintext) contents of a text message and send it to the other party. Note that bytes can be any byte sequence, not necessarily a valid UTF-8 sequence. The result to this query is the ciphertext corresponding to the given plaintext.

- MSG [A|B] bytes — send a specified (ciphertext) message (for example, obtained as an answer to an ASK or TXT query) to A or B. You will receive ‘Ok’ if this message was decrypted successfully and accepted by the client, or ‘Fail’ otherwise.

Example:

---

### Objectives

We are offering a $300,000 reward to the first person to break Telegram's encryption protocol in this contest.

Your goal is to extract a secret email address from one of the random messages that are exchanged between Nick and Paul when you use the ASK command. It is guaranteed that at least one of the first ten generated messages within a session will contain the secret address. It is also guaranteed that apart from that, all messages will contain only dictionary English words, spaces, line breaks and punctuation marks.

Once you have the address, you will need to send an email to it. That email must contain:- The entire text of the message that contained the secret email.- Session logs for the successful attempt with your user_id.- A detailed explanation of the attack on the protocol.- Your bank account details to receive the $300,000 prize.

#### Decrypting messages

To prove that the competition was fair, we will add a command that returns the keys used for a particular session by its session_id at the end of the contest. This will be done as soon as a winner is announced, or on February 4, 2015 in case no winner is announced to that date.

#### Bonus objective

We are also offering an independent $100,000 reward to the first person to make the bot accept a ciphertext message (i.e. the first person to send a message using MSG [A|B] bytes and receive the result ‘OK’), provided that that ciphertext deciphers to a plaintext that was never encrypted by the bot itself within this session.

Should you succeed at this, kindly send an email to security@telegram.org and include the following:- Session logs for the successful attempt with your user_id.- A detailed explanation of the attack on the protocol.- Your bank account details to receive the $100,000 prize.

