# Scheduled messages

Telegram allows scheduling messages.

To schedule a message, simply provide a future unixtime in the schedule_date flag of messages.sendMessage or messages.sendMedia.

The specified message or media will be added to a server-side schedule queue for the current chat, and will be automatically sent at the specified time.
The method call generates the following updates:

- Immediately, an updateNewScheduledMessage, with ID equal to the ID of the message in the schedule queue for the current chat (each PM, chat, supergroup and channel has its own schedule queue and ID sequence).

- At schedule_date, an updateNewMessage or updateNewChannelMessage with the from_scheduled flag set, indicating to the sender that the specified scheduled message was sent.

- At schedule_date, an updateDeleteScheduledMessages, indicating that the message was flushed from the schedule queue.

If the schedule_date is less than 10 seconds in the future, the message will be sent immediately, generating a normal updateNewMessage/updateNewChannelMessage.

### Manipulating the schedule queue

Clients can manually edit the schedule queue of a certain chat, providing the scheduled message ID obtained from updateNewScheduledMessage.

- messages.getScheduledHistory obtains all messages in the schedule queue for the specified chat

- messages.getScheduledMessages obtains information about specific messages in the schedule queue for the specified chat

- messages.sendScheduledMessages flushes messages from the schedule queue, sending them immediately

- messages.deleteScheduledMessages deletes messages from the schedule queue, without sending them

- messages.editMessage can be used to modify the scheduled date of a specific message in a schedule queue.

Modifying scheduled messages will generate an updateNewScheduledMessage with the same ID, and updated information.
Deleting scheduled messages will generate an updateDeleteScheduledMessages.

