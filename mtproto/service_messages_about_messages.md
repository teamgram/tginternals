# ﻿Service Messages about Messages

#### Acknowledgment of Receipt

Receipt of virtually all messages (with the exception of some purely service ones as well as the plain-text messages used in the protocol for creating an authorization key) must be acknowledged.This requires the use of the following service message (not requiring an acknowledgment):

A server usually acknowledges the receipt of a message from a client (normally, an RPC query) using an RPC response. If a response is a long time coming, a server may first send a receipt acknowledgment, and somewhat later, the RPC response itself.

A client normally acknowledges the receipt of a message from a server (usually, an RPC response) by adding an acknowledgment to the next RPC query if it is not transmitted too late (if it is generated, say, 60-120 seconds following the receipt of a message from the server). However, if for a long period of time there is no reason to send messages to the server or if there is a large number of unacknowledged messages from the server (say, over 16), the client transmits a stand-alone acknowledgment.

Max 8192 IDs are allowed per constructor.

#### Notice of Ignored Error Message

In certain cases, a server may notify a client that its incoming message was ignored for whatever reason. Note that such a notification cannot be generated unless a message is correctly decoded by the server.

Here, error_code can also take on the following values:

- 16:  msg_id too low (most likely, client time is wrong; it would be worthwhile to synchronize it using msg_id notifications and re-send the original message with the “correct” msg_id or wrap it in a container with a new msg_id if the original message had waited too long on the client to be transmitted)

- 17: msg_id too high (similar to the previous case, the client time has to be synchronized, and the message re-sent with the correct msg_id)

- 18: incorrect two lower order msg_id bits (the server expects client message msg_id to be divisible by 4)

- 19: container msg_id is the same as msg_id of a previously received message (this must never happen)

- 20: message too old, and it cannot be verified whether the server has received a message with this msg_id or not

- 32: msg_seqno too low (the server has already received a message with a lower msg_id but with either a higher or an equal and odd seqno)

- 33: msg_seqno too high (similarly, there is a message with a higher msg_id but with either a lower or an equal and odd seqno)

- 34: an even msg_seqno expected (irrelevant message), but odd received

- 35: odd msg_seqno expected (relevant message), but even received

- 48: incorrect server salt (in this case, the bad_server_salt response is received with the correct salt, and the message is to be re-sent with it)

- 64: invalid container.

The intention is that error_code values are grouped (error_code >> 4): for example, the codes 0x40 - 0x4f  correspond to errors in container decomposition.

Notifications of an ignored message do not require acknowledgment (i.e., are irrelevant).

Important: if server_salt has changed on the server or if client time is incorrect, any query will result in a notification in the above format. The client must check that it has, in fact, recently sent a message with the specified msg_id, and if that is the case, update its time correction value (the difference between the client's and the server's clocks) and the server salt based on msg_id and the server_salt notification, so as to use these to (re)send future messages. In the meantime, the original message (the one that caused the error message to be returned) must also be re-sent with a better msg_id and/or server_salt.

In addition, the client can update the server_salt value used to send messages to the server, based on the values of RPC responses or containers carrying an RPC response, provided that this RPC response is actually a match for the query sent recently. (If  there is doubt, it is best not to update since there is risk of a replay attack).

#### Request for Message Status Information

If either party has not received information on the status of its outgoing messages for a while, it may explicitly request it from the other party:

Max 8192 IDs are allowed per constructor.

The response to the query contains the following information:

#### Informational Message regarding Status of Messages

Here, info is a string that contains exactly one byte of message status for each message from the incoming msg_ids list:

- 1 = nothing is known about the message (msg_id too low, the other party may have forgotten it)

- 2 = message not received (msg_id falls within the range of stored identifiers; however, the other party has certainly not received a message like that)

- 3 = message not received (msg_id too high; however, the other party has certainly not received it yet)

- 4 = message received (note that this response is also at the same time a receipt acknowledgment)

- +8 = message already acknowledged

- +16 = message not requiring acknowledgment

- +32 = RPC query contained in message being processed or processing already complete

- +64 = content-related response to message already generated

- +128 = other party knows for a fact that message is already received

This response does not require an acknowledgment. It is an acknowledgment of the relevant msgs_state_req, in and of itself.

Note that if it turns out suddenly that the other party is missing a message that appears to have been sent to it, the message must not be re-sent on its own with the same msg_id. Instead, it can be either wrapped in a container, or the status of the message can be checked using msgs_state_req and if the message wasn't received, then it must be re-sent with a new msg_id.

#### Voluntary Communication of Status of Messages

Either party may voluntarily inform the other party of the status of the messages transmitted by the other party.

All message codes known to this party are enumerated, with the exception of those for which the +128 and the +16 flags are set. However, if the +32 flag is set but not +64, then the message status will still be communicated.

This message does not require an acknowledgment.

#### Extended Voluntary Communication of Status of One Message

Normally used by the server to respond to the receipt of a duplicate msg_id, especially if a response to the message has already been generated and the response is large. If the response is small, the server may re-send the answer itself instead. This message can also be used as a notification instead of resending a large message.

The second version is used to notify of messages that were created on the server not in response to an RPC query (such as notifications of new messages) and were transmitted to the client some time ago, but not acknowledged.

Currently, status is always zero. This may change in future.

This message does not require an acknowledgment.

#### Explicit Request to Re-Send Messages

The remote party immediately responds by re-sending the requested messages, normally using the same connection that was used to transmit the query. If at least one message with requested msg_id does not exist or has already been forgotten, or has been sent by the requesting party (known from parity), MsgsStateInfo is returned for all messages requested as if the MsgResendReq query had been a MsgsStateReq query as well.Max 8192 IDs are allowed per constructor.

