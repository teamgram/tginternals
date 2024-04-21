# messages.getDhConfig
Returns configuration parameters for Diffie-Hellman key generation. Can also return a random sequence of bytes of required length.

```
messages.dhConfigNotModified#c0e24635 random:bytes = messages.DhConfig;
messages.dhConfig#2c221edd g:int p:bytes version:int random:bytes = messages.DhConfig;
---functions---
messages.getDhConfig#26cf8950 version:int random_length:int = messages.DhConfig;
```

## Parameters
| Name | Type | Description |
| ---- | :----: | ----------- |
| version | int | Value of the version parameter from messages.dhConfig, available at the client |
| random_length | int | Length of the required random sequence |


## Result
messages.DhConfig

## Possible errors
| Code | Type | Description |
| ---- | :----: | ----------- |
| 400 | RANDOM_LENGTH_INVALID | Random length invalid. |

