# DataJSON
Represent a JSON-encoded object

```
dataJSON#7d748d04 data:string = DataJSON;

---functions---

bots.sendCustomRequest#aa2769ed custom_method:string params:DataJSON = DataJSON;
bots.invokeWebViewCustomMethod#87fc5e7 bot:InputUser custom_method:string params:DataJSON = DataJSON;

phone.getCallConfig#55451fa9 = DataJSON;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| dataJSON | Represents a json-encoded object |


## Methods
| Method | Description |
| ---- | ----------- |
| bots.sendCustomRequest | Sends a custom request; for bots only |
| phone.getCallConfig | Get phone call configuration to be passed to libtgvoip's shared config |
| bots.invokeWebViewCustomMethod | Send a custom request from a mini bot app, triggered by a web_app_invoke_custom_method event ».The response should be sent using a custom_method_invoked event, see here » for more info on the flow. |


