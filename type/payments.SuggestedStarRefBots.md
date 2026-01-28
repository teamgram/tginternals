# Payments.SuggestedStarRefBots
A list of suggested mini apps with available affiliate programs

```
payments.suggestedStarRefBots#b4d5d859 flags:# count:int suggested_bots:Vector<StarRefProgram> users:Vector<User> next_offset:flags.0?string = payments.SuggestedStarRefBots;

---functions---

payments.getSuggestedStarRefBots#d6b48f7 flags:# order_by_revenue:flags.0?true order_by_date:flags.1?true peer:InputPeer offset:string limit:int = payments.SuggestedStarRefBots;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| payments.suggestedStarRefBots | A list of suggested mini apps with available affiliate programs |


## Methods
| Method | Description |
| ---- | ----------- |
| payments.getSuggestedStarRefBots | Obtain a list of suggested mini apps with available affiliate programsorder_by_revenue and order_by_date are mutually exclusive: if neither is set, results are sorted by profitability. |


