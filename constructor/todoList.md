# todoList
Represents a todo list ».

```
todoList#49b92a26 flags:# others_can_append:flags.0?true others_can_complete:flags.1?true title:TextWithEntities list:Vector<TodoItem> = TodoList;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| others_can_append | flags.0?true | If set, users different from the creator of the list can append items to the list. |
| others_can_complete | flags.1?true | If set, users different from the creator of the list can complete items in the list. |
| title | TextWithEntities | Title of the todo list, maximum length equal to todo_title_length_max ». |
| list | Vector<TodoItem> | Items of the list. |


## Type
TodoList

## Related pages
