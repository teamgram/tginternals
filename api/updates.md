# Working with Updates

When a client is being actively used, events will occur that affect the current user and that they must learn about as soon as possible, e.g. when a new message is received. To eliminate the need for the client itself to periodically download these events, there is an update delivery mechanism in which the server sends the user notifications over one of its available connections with the client.

### Subscribing to Updates

Update events are sent to an authorized user into the last active connection (except for connections needed for downloading / uploading files).

So to start receiving updates the client needs to init connection and call API method, e.g. to fetch current state.

### Event sequences

All events are received from the socket as a sequence of TL-serialized Updates objects, which might be optionally gzip-compressed in the same way as responses to queries.

Each Updates object may contain single or multiple Update objects, representing different events happening.

In order to apply all updates in precise order and to guarantee that no update is missed or applied twice there is seq attribute in Updates constructors, and pts (with pts_count) or qts attributes in Update constructors. The client must use those attributes values in combination with locally stored state to correctly apply incoming updates.

When a gap in updates sequence occurs, it must be filled via calling one of the API methods. More below »

### Updates sequence

As said earlier, each payload with updates has a TL-type Updates. It can be seen from the schema below that this type has several constructors.

updatesTooLong indicates that there are too many events pending to be pushed to the client, so one needs to fetch them manually.

Events inside updateShort constructors, normally, have lower priority and are broadcast to a large number of users, i.e. one of the chat participants started entering text in a big conversation (updateChatUserTyping).

The updateShortMessage, updateShortSentMessage and updateShortChatMessage constructors are redundant but help significantly reduce the transmitted message size for 90% of the updates. They should be transformed to updateShort upon receival.

Two remaining constructors updates and updatesCombined are part of the Updates sequence. Both of them have the seq attribute, which indicates the remote Updates state after the generation of the Updates, and seq_start indicates the remote Updates state after the first of the Updates in the packet is generated. For updates, the seq_start attribute is omitted, because it is assumed that it is always equal to seq.

### Message-related event sequences

Each event related to a message box (message created, message edited, message deleted, etc) is identified by a unique autoincremented pts, or qts in case of secret chat updates, certain bot updates, etc.

Each message box can be considered as some server-side DB table that stores messages and events associated with them.
All boxes are completely independent, and each pts sequence is tied to just one box (see below).

The Update object may contain info about multiple events (for example, updateDeleteMessages).
That's why all single updates might have pts_count parameter indicating the number of events contained in the received update (with some exceptions, in this case, the pts_count is considered to be 0).

Each channel and supergroup has its message box and its event sequence as a result; private chats and basic groups of one user have another common event sequence.
Secret chats, certain bot events and other kinds of updates have yet another common secondary event sequence.

To recap, the client has to take care of the integrity of the following sequences to properly handle updates:

- Updates sequence (seq)

- Common message box sequence (pts)

- Secondary event sequence (qts)

- Channel message box sequence 1 (pts)

- Channel message box sequence 2 (pts)

- Channel message box sequence 3 (pts)

- and so on...

### Fetching state

The common update state is represented by the updates.State constructor.
When the user logs in for the first time, a call to updates.getState has to be made to store the latest update state (which will not be the absolute initial state, just the latest state at the current time).
The common update state can also be fetched from updates.differenceTooLong.

The channel update state is represented simply by the pts of the event sequence: when first logging in, the initial channel state can be obtained from the dialog constructor when fetching dialogs, from the full channel info, or it can be received as an updateChannelTooLong update.

The secondary update state is represented by the qts of the secret event sequence, it is contained in the updates.State of the common update state.

The Updates sequence state is represented by the date and seq of the Updates sequence, it is contained in the updates.State of the common update state.

### Update handling

Update handling in Telegram clients consists of receiving events, making sure there were no gaps and no events were missed based on the locally stored state of the correspondent event sequence, and then updating the locally stored state based on the parameters received.

When the client receives payload with serialized updates, first of all, it needs to walk through all of the nested Update objects and check if they belong to any of message box sequences (have pts or qts parameters). Those updates need to be handled separately according to corresponding local state and new pts/qts values. Details below »

After message box updates are handled, if there are any other updates remaining the client needs to handle them with respect to seq. Details below »

#### pts: checking and applying

Here, local_pts will be the local state, pts will be the remote state, pts_count will be the number of events in the update.

- If local_pts + pts_count === pts, the update can be applied.

- If local_pts + pts_count > pts, the update was already applied, and must be ignored.

- If local_pts + pts_count < pts, there's an update gap that must be filled.

For example, let's assume the client has the following local state for the channel 123456789:

Now let's assume an updateNewChannelMessage from channel 123456789 is received with pts = 132 and pts_count=1.
Since local_pts + pts_count === pts, the total number of events since the last stored state is, in fact, equal to pts_count: this means the update can be safely accepted and the remote pts applied:

Since:

- pts indicates the server state after the new channel message events are generated

- pts_count indicates the number of events in the new channel update

- The server state before the new channel message event was generated has to be: pts_before = pts - pts_count = 131, which is, in fact, equal to our local state.

Now let's assume an updateNewChannelMessage from channel 123456789 is received with pts = 132 and pts_count=1.
Since local_pts + pts_count > pts (133 > 132), the update is skipped because we've already handled this update (in fact, our current local_pts was set by this same update, and it was resent twice due to network issues or other issues).

Now let's assume an updateDeleteChannelMessages from channel 123456789 is received with pts = 140 and pts_count=5.
Since local_pts + pts_count < pts (137 < 140), this means that updates were missed, and the gap must be recovered.

##### Secret chats & bots

The whole process is very similar for secret chats and certain bot updates, but there is a qts instead of pts, and events are never grouped, so it's assumed that qts_count is always equal to 1.

#### seq: checking and applying

On the top level when handling received updates and updatesCombined there are four possible cases:

- If seq_start === 0, the updates can be applied: this is a special case for updates that aren't ordered and should just be applied immediately.

- If local_seq + 1 === seq_start, the updates can be applied.

- If local_seq + 1 > seq_start, the updates were already applied, and must be ignored.

- If local_seq + 1 < seq_start, there's an updates gap that must be filled (updates.getDifference must be used as with common and secret event sequences).

If the updates were applied, local Updates state must be updated with seq (unless it's 0) and date from the constructor.

For all the other Updates type constructors there is no need to check seq or change a local state.

### Recovering gaps

To do this, updates.getDifference (common/secret state) or updates.getChannelDifference (channel state) with the respective local states must be called.
These methods should also be called on startup, to fetch new updates (preferably with some flags to reduce server load, see the method's docs).
Manually obtaining updates is also required in the following situations:

- Loss of sync: a gap was found in  seq / pts / qts (as described above). It may be useful to wait up to 0.5 seconds in this situation and abort the sync in case a new update arrives, that fills the gap.

- Session loss on the server: the client receives a new session created notification. This can be caused by garbage collection on the MTProto server or a server reboot.

- Incorrect update: the client cannot deserialize the received data.

- Incomplete update: the client is missing data about a chat/user from one of the shortened constructors, such as updateShortChatMessage, etc.

- Long period without updates: no updates for 15 minutes or longer.

- The server requests the client to fetch the difference using updateChannelTooLong or updatesTooLong.

When calling updates.getDifference if the updates.differenceSlice constructor is returned in response, the full difference was too large to be received in one request. The intermediate status, intermediate_state, must be saved on the client and the query must be repeated, using the intermediate status as the current status.

To fetch the updates difference of a channel, updates.getChannelDifference is used.
If the difference is too large to be received in one request, the final flag of the result is not set (see docs).
The intermediate status, represented by the pts, must be saved on the client and the query must be repeated, using the intermediate status as the current status.

For performance reasons and for better user experience, client can set maximum gap size to be filled: pts_total_limit parameter of updates.getDifference and limit parameter for updates.getChannelDifference can be used.

If the gap is too large and there are too many updates to fetch, a *TooLong constructor will be returned. In this case, the client must re-fetch the state, re-start fetching updates from that state and follow the instructions that can be found here.

It is recommended to use limit 10-100 for channels and 1000-10000 otherwise.

### Subscribing to updates of channels/supergroups we haven't joined

Clients may ask the API to passively send them updates for channels/supergroups they haven't joined, by simply making a updates.getChannelDifference query.

If the specified channel or supergroup is public, or is private but temporarily available for a limited time thanks to a chatInvitePeek, the API will start passively sending updates (i.e. as standalone Updates constructors in the socket, as is already the case for normal channels/supergroups we've already joined) to all logged-in sessions, as long as any of the sessions continues to periodically invoke updates.getChannelDifference every timeout seconds (returned by the method, or every 10 seconds if the timeout flag is absent from the return value of the method).

To stop passively receiving updates, simply stop invoking updates.getChannelDifference, and the API will automatically stop passively sending updates after a while.

### Example implementations

Implementations also have to take care to postpone updates received via the socket while filling gaps in the event and Update sequences, as well as avoid filling gaps in the same sequence.

Example implementations: tdlib, MadelineProto.

An interesting and easy way this can be implemented, instead of using various locks, is by running background loops, like in MadelineProto ».

### PUSH Notifications about Updates

If a client does not have an active connection at the time of an event, PUSH Notifications will also be useful.

