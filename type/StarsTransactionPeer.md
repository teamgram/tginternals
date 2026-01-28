# StarsTransactionPeer
Source of an incoming Telegram Star transaction, or its recipient for outgoing Telegram Star transactions.

```
starsTransactionPeerUnsupported#95f2bfe4 = StarsTransactionPeer;
starsTransactionPeerAppStore#b457b375 = StarsTransactionPeer;
starsTransactionPeerPlayMarket#7b560a0b = StarsTransactionPeer;
starsTransactionPeerPremiumBot#250dbaf8 = StarsTransactionPeer;
starsTransactionPeerFragment#e92fd902 = StarsTransactionPeer;
starsTransactionPeer#d80da15d peer:Peer = StarsTransactionPeer;
starsTransactionPeerAds#60682812 = StarsTransactionPeer;
starsTransactionPeerAPI#f9677aad = StarsTransactionPeer;
```

## Constructors
| Constructor | Description |
| ---- | ----------- |
| starsTransactionPeerUnsupported | Describes a Telegram Star transaction that cannot be described using the current layer. |
| starsTransactionPeerAppStore | Describes a Telegram Star transaction with the App Store, used when purchasing Telegram Stars through the App Store. |
| starsTransactionPeerPlayMarket | Describes a Telegram Star transaction with the Play Store, used when purchasing Telegram Stars through the Play Store. |
| starsTransactionPeerPremiumBot | Describes a Telegram Star transaction made using @PremiumBot (i.e. using the inputInvoiceStars flow described here »). |
| starsTransactionPeerFragment | Describes a Telegram Star transaction with Fragment, used when purchasing Telegram Stars through Fragment. |
| starsTransactionPeer | Describes a Telegram Star transaction with another peer. |
| starsTransactionPeerAds | Describes a Telegram Star transaction used to pay for Telegram ads as specified here ». |
| starsTransactionPeerAPI | Describes a Telegram Star transaction used to pay for paid API usage, such as paid bot broadcasts. |


## Methods
| Method | Description |
| ---- | ----------- |


