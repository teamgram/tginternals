# Top peer rating

If enabled, the rating of top peers indicates the relevance of a frequently used peer in a certain category (frequently messaged users, frequently used bots, inline bots, frequently visited channels and so on).

Schema:

Use contacts.toggleTopPeers to enable or disable top peer ratings.

The rate delta is computed by taking the time delta between the last time the user used a certain peer and the last time the rating for that peer was received and dividing it by the exponential decay from config.

Example:
Client-side, every time a user opens chat 123456789 the following operation must be done on the cached top peer info.

- dateOpened indicates when was the peer used

- normalizeRate is an arbitrary time in the recent past.

- When ratings are received from the server using contacts.getTopPeers and the schema described above, it is the time when they were received.

Use contacts.resetTopPeerRating to reset the top peer rating of a certain peer, in a certain category.

