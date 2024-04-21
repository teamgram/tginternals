# messages.Reactions
A set of message reactions

```
messages.reactionsNotModified#b06fdbdf = messages.Reactions;
messages.reactions#eafdf716 hash:long reactions:Vector<Reaction> = messages.Reactions;

---functions---

messages.getTopReactions#bb8125ba limit:int hash:long = messages.Reactions;
messages.getRecentReactions#39461db2 limit:int hash:long = messages.Reactions;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.reactionsNotModified | The server-side list of message reactions hasn't changed |
| messages.reactions | List of message reactions |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getTopReactions | Got popular message reactions |
| messages.getRecentReactions | Get recently used message reactions |


