# Imported messages
Telegram allows importing messages and media from foreign chat apps.
> Note: This article is intended for MTProto API developers. If you're looking for a way to move history from other chat apps into Telegram, check out the related Telegram blog post.
### 1. Validate the chat export file
The import process begins by calling messages.checkHistoryImport, passing to import_head up to 100 lines of the chat export file, starting from the beginning of the file.
The returned constructor contains information about the exported chat, including its title or type.
If the pm flag is set, the chat export file was generated from a private chat.
If the group flag is set, the chat export file was generated from a group chat.
If neither the pm or group flags are set, the specified chat export was generated from a chat of unknown type.
### 2. Choosing a destination Telegram chat
Using messages.checkHistoryImportPeer, check whether chat history exported from another chat app can be imported into a specific Telegram peer, chosen by the user.
Typically, history imports are allowed for private chats with a mutual contact or supergroups with change_info administrator rights ».
If the check succeeds, and no RPC errors are returned, a messages.CheckedHistoryImportPeer constructor will be returned, with a confirmation text to be shown to the user in a confirmation prompt.
Upon final user confirmation, the import process is initialized.
### 3. Initialize the import
Use messages.initHistoryImport to initialize the import process, passing the following parameters:
- peer - The Telegram chat where the history should be imported.
- file - The chat export file.
- media_count - The number of media files associated with the export, to be uploaded in the next step.
### 4. Uploading media
Use messages.uploadImportedMedia to upload media files eventually associated with the chat export.
import_id is the id contained in the messages.historyImport constructor, returned by messages.initHistoryImport in the previous step.
### 5. Finalize the import
Finally, invoke messages.startHistoryImport to complete the history import process, importing all messages into the chat.
As usual, import_id is the id contained in the messages.historyImport constructor, returned by messages.initHistoryImport.
Imported messages will show in the chat history as messages containing a fwd_from messageFwdHeader constructor with the imported flag, and should be appropriately marked in the UI as messages imported from a foreign chat app.
