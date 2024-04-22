# Blocklist
Working with the blocklist.
Scheme:
Use contacts.block and contacts.unblock to block and unblock peers.
If the my_stories_from is set, peers will be added/removed only to/from the story blocklist; otherwise, they will be added/removed to/from the the main blocklist.
Peers in the story blocklist won't be able view your stories.
Peers in the main blocklist won't be able to write messages to you, view your status, photo and stories.
Adding or removing a peer from a blocklist will emit an updatePeerBlocked to all currenly logged-in sessions (the peer we blocked/unblocked won't receive any update).
Use contacts.getBlocked to fetch the list of blocked peers; as usual, the my_stories_from flag can be used to fetch the story blocklist or the main blocklist, and the offset/limit parameters are used for pagination ».
contacts.setBlocked may also be used to completely replace the contents of an entire blocklist in bulk: just pass the blocklist type in my_stories_from, the full list of IDs to block in id and the length of the list passed to id in limit: the server will completely replace the specified blocklist.
