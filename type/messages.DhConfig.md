# Messages.DhConfig
Contains Diffie-Hellman key generation protocol parameters.

```
messages.dhConfigNotModified#c0e24635 random:bytes = messages.DhConfig;
messages.dhConfig#2c221edd g:int p:bytes version:int random:bytes = messages.DhConfig;

---functions---

messages.getDhConfig#26cf8950 version:int random_length:int = messages.DhConfig;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| messages.dhConfigNotModified | Configuring parameters did not change. |
| messages.dhConfig | New set of configuring parameters. |


## Methods
| Method | Description |
| ---- | ----------- |
| messages.getDhConfig | Returns configuration parameters for Diffie-Hellman key generation. Can also return a random sequence of bytes of required length. |


