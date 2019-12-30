# Create an advanced account

## KeyList

A KeyList requires all public keys added to the account to sign

| Constructor | Description |
| :--- | :--- |
| `KeyList()` | Initializes the KeyList object |

```java
new KeyList().addKey()
```

| Method | Type | Description |
| :--- | :--- | :--- |
| `addKey(<publicKey>)` | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) | Adds the public key to the account. Can be used multiple times to add multiple public keys.  |

### Example

```java
TransactionId account = new AccountCreateTransaction()  
    // All three signatures required 
    .setKey(new KeyList().addKey(publicKey1).addKey(publicKey2).addKey(publicKey3))
    .setInitialBalance(1000000)
    .setAutoRenewPeriod(Duration.ofSeconds(7890000))
    .setTransactionFee(80000000)
    .build(client);
```

## Threshold Key

| Constructor | Description |
| :--- | :--- |
| `ThresholdKey()` | Initializes the ThresholdKey object |

| Method | Type | Description |
| :--- | :--- | :--- |
|  | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) |  |

```text

```

## Nested Keys

| Method | Type | Description |
| :--- | :--- | :--- |
|  | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) |  |

```text

```

