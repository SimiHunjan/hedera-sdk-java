# Accounts & Keys

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
TransactionId accountKeyList = new AccountCreateTransaction()  
    // All three signatures required 
    .setKey(new KeyList().addKey(publicKey1).addKey(publicKey2).addKey(publicKey3))
    .setInitialBalance(1000000)
    .setAutoRenewPeriod(Duration.ofSeconds(7890000))
    .setTransactionFee(80000000)
    .build(client);
```

## Threshold Key

Requires a minimum of x number of signatures from a total of y signatures to modify the account.

| Constructor | Type | Description |
| :--- | :--- | :--- |
| `ThresholdKey(<thresholdValue>)` | int | Initializes the ThresholdKey object and takes the int value represents the minimum number of signatures required to modify the account |

```java
new ThresholdKey().addAll()
```

| Method | Type | Description |
| :--- | :--- | :--- |
| `addAll(<keys>)` | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) | The public keys to add to the account |

### Example

```java
TransactionId accountThresholdKeys = new AccountCreateTransaction()  
  //2 out 3 signatures required
    .setKey(new ThresholdKey(2).addAll(key1,key2,key3)
    .setInitialBalance(1000000)
    .setAutoRenewPeriod(Duration.ofSeconds(7890000))
    .setTransactionFee(80000000)
    .build(client);
```

