# phoneCallProtocol
Protocol info for libtgvoip

```
phoneCallProtocol#fc878fc8 flags:# udp_p2p:flags.0?true udp_reflector:flags.1?true min_layer:int max_layer:int library_versions:Vector<string> = PhoneCallProtocol;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| flags | # | Flags, see TL conditional fields |
| udp_p2p | flags.0?true | Whether to allow P2P connection to the other participant |
| udp_reflector | flags.1?true | Whether to allow connection to the other participants through the reflector servers |
| min_layer | int | Minimum layer for remote libtgvoip |
| max_layer | int | Maximum layer for remote libtgvoip |
| library_versions | Vector<string> | When using phone.requestCall and phone.acceptCall, specify all library versions supported by the client. The server will merge and choose the best library version supported by both peers, returning only the best value in the result of the callee's phone.acceptCall and in the phoneCallAccepted update received by the caller. |


## Type
PhoneCallProtocol

## Related pages
