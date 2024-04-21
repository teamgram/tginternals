# StatsGraph
Channel statistics graph

```
statsGraphAsync#4a27eb2d token:string = StatsGraph;
statsGraphError#bedc9822 error:string = StatsGraph;
statsGraph#8ea464b6 flags:# json:DataJSON zoom_token:flags.0?string = StatsGraph;

---functions---

stats.loadAsyncGraph#621d5fa0 flags:# token:string x:flags.0?long = StatsGraph;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| statsGraphAsync | This channel statistics graph must be generated asynchronously using stats.loadAsyncGraph to reduce server load |
| statsGraphError | An error occurred while generating the statistics graph |
| statsGraph | Channel statistics graph |


## Methods
| Method | Description |
| ---- | ----------- |
| stats.loadAsyncGraph | Load channel statistics graph asynchronously |


