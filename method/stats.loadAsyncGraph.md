# stats.loadAsyncGraph
Load channel statistics graph asynchronously

```
statsGraphAsync#4a27eb2d token:string = StatsGraph;
statsGraphError#bedc9822 error:string = StatsGraph;
statsGraph#8ea464b6 flags:# json:DataJSON zoom_token:flags.0?string = StatsGraph;
---functions---
stats.loadAsyncGraph#621d5fa0 flags:# token:string x:flags.0?long = StatsGraph;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| token | string | Graph token from statsGraphAsync constructor |
| x | flags.0?long | Zoom value, if required |


## Result
StatsGraph

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | GRAPH_EXPIRED_RELOAD | This graph has expired, please obtain a new graph token. |
| 400 | GRAPH_INVALID_RELOAD | Invalid graph token provided, please reload the stats and provide the updated token. |
| 400 | GRAPH_OUTDATED_RELOAD | The graph is outdated, please get a new async token using stats.getBroadcastStats. |

