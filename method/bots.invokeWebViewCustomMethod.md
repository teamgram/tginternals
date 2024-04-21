# bots.invokeWebViewCustomMethod
Send a custom request from a mini bot app, triggered by a web_app_invoke_custom_method event ».

```
dataJSON#7d748d04 data:string = DataJSON;
---functions---
bots.invokeWebViewCustomMethod#87fc5e7 bot:InputUser custom_method:string params:DataJSON = DataJSON;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| bot | InputUser | Identifier of the bot associated to the mini bot app |
| custom_method | string | Identifier of the custom method to invoke |
| params | DataJSON | Method parameters |


## Result


## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | BOT_INVALID | This is not a valid bot. |

