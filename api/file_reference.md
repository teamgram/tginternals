# File references
They must be cached by the client, along with the origin context where the document/photo object was found, in order to be refetched when the file reference expires.
Example implementation of a reference database: MadelineProto, android, telegram desktop, tdlib.
#### Another example:
Assume you receive a message from your friend: that message contains a messageMediaPhoto with a photo.
Your client has to cache not only the file_reference field of the photo, but also the context in which the file reference was seen (in this case, a message coming from a specific user).
The context info is in this case, an origin context of type message, containing the message ID and the peer ID of the chat/channel/user where the message was seen.
The context info has to be associated with the file reference: when downloading a file using upload.getFile, a FILE_REFERENCE_EXPIRED error (or another error starting with FILE_REFERENCE_) may be returned.
If this happens, the context info must be used to refetch the object that contained the file reference: in this example, the peer info and the message ID have to be used with channels.getMessages or messages.getMessages to refetch the message, recache the file reference and use it in a new file download request.
More than one origin context can be associated to one file reference, for greater resilience (in the case of a message that was deleted in one chat but was also forwarded in another chat, the file reference can be refetched from the second chat, instead).
Origin contexts for objects returned by method calls with certain parameters can be considered, too (for example, in the case of favorited sticker sets returned by messages.getFavedStickers).
