# Todo

Premium users can now create collaborative checklists in any chat to track tasks and coordinate teams — or manage shopping and to-do lists.

### Todo lists

```
todoItem#cba9a52f id:int title:TextWithEntities = TodoItem;
todoList#49b92a26 flags:# others_can_append:flags.0?true others_can_complete:flags.1?true title:TextWithEntities list:Vector<TodoItem> = TodoList;

inputMediaTodo#9fc55fde todo:TodoList = InputMedia;

messageMediaToDo#8a53b014 flags:# todo:TodoList completions:flags.0?Vector<TodoCompletion> = MessageMedia;

messageActionTodoCompletions#cc7c5c89 completed:Vector<int> incompleted:Vector<int> = MessageAction;
messageActionTodoAppendTasks#c7edbc83 list:Vector<TodoItem> = MessageAction;

---functions---

messages.sendMedia#ac55d9c1 flags:# silent:flags.5?true background:flags.6?true clear_draft:flags.7?true noforwards:flags.14?true update_stickersets_order:flags.15?true invert_media:flags.16?true allow_paid_floodskip:flags.19?true peer:InputPeer reply_to:flags.0?InputReplyTo media:InputMedia message:string random_id:long reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.10?int send_as:flags.13?InputPeer quick_reply_shortcut:flags.17?InputQuickReplyShortcut effect:flags.18?long allow_paid_stars:flags.21?long suggested_post:flags.22?SuggestedPost = Updates;

messages.appendTodoList#21a61057 peer:InputPeer msg_id:int list:Vector<TodoItem> = Updates;

messages.toggleTodoCompleted#d3e03124 peer:InputPeer msg_id:int completed:Vector<int> incompleted:Vector<int> = Updates;

messages.editMessage#dfd14005 flags:# no_webpage:flags.1?true invert_media:flags.16?true peer:InputPeer id:int message:flags.11?string media:flags.14?InputMedia reply_markup:flags.2?ReplyMarkup entities:flags.3?Vector<MessageEntity> schedule_date:flags.15?int quick_reply_shortcut_id:flags.17?int = Updates;
```

Use messages.sendMedia with inputMediaTodo to post a to-do list.

The title of a todo list has a maximum length equal to todo_title_length_max ».

During creation, todoList.others_can_append can be set to allow users different from yourself to invoke messages.appendTodoList to append items to the list.
todoList.others_can_complete can be set to allow users different from yourself to mark items as (not) completed with messages.toggleTodoCompleted.

The passed todoItems are composed of a title (maximum length equal to todo_item_length_max ») and a positive (non-zero) ID, unique within the context of the current list.

A todo list can have at most todo_items_max » items.

Use messages.appendTodoList to append items to the to-do list after creation: this will emit service messages of type messageActionTodoAppendTasks.
The newly appended todoItems must have an ID that isn't already contained within the item list, otherwise a TODO_ITEM_DUPLICATE RPC error will be emitted.

Use messages.toggleTodoCompleted to toggle some items as completed or not completed using their IDs: this will emit service messages of type messageActionTodoCompletions.

messages.editMessage can be used to remove tasks from the list, by re-specifying a modified copy of the existing todoList as an inputMediaTodo: removing items in this manner will not erase the completion tasks of non-deleted items, as long as their IDs aren't changed.
The same method can also be used in the same manner to add multiple tasks to the list without emitting a messageActionTodoAppendTasks service message.

#### Reply to specific tasks

```
inputReplyToMessage#869fbe10 flags:# reply_to_msg_id:int top_msg_id:flags.0?int reply_to_peer_id:flags.1?InputPeer quote_text:flags.2?string quote_entities:flags.3?Vector<MessageEntity> quote_offset:flags.4?int monoforum_peer_id:flags.5?InputPeer todo_item_id:flags.6?int = InputReplyTo;

messageReplyHeader#6917560b flags:# reply_to_scheduled:flags.2?true forum_topic:flags.3?true quote:flags.9?true reply_to_msg_id:flags.4?int reply_to_peer_id:flags.0?Peer reply_from:flags.5?MessageFwdHeader reply_media:flags.8?MessageMedia reply_to_top_id:flags.1?int quote_text:flags.6?string quote_entities:flags.7?Vector<MessageEntity> quote_offset:flags.10?int todo_item_id:flags.11?int = MessageReplyHeader;
```

Clients can send messages in reply to specific items of todo lists, through the todo_item_id field of inputReplyToMessage and messageReplyHeader, set when replying to todo lists.

