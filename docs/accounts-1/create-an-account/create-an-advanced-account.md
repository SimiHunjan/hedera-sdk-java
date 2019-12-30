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
| `addKey(<publicKey>)` | PublicKey | Adds the public key to the account. Can be used multiple times to add multiple public keys.  |

### Example

```java
var account = new AccountCreateTransaction(client).  
  //All three signatures required 
    .setKey(new KeyList().addKey(publicKey1).addKey(publicKey2).addKey(publicKey3))
    .setInitialBalance(1000000)
    .setAutoRenewPeriod(Duration.ofSeconds(7890000))
    .setTransactionFee(80000000)
    .executeForReceipt();
```

## Threshold Key

| Method | Type | Description |
| :--- | :--- | :--- |
|  |  |  |

```text

```

## Nested Keys

| Method | Type | Description |
| :--- | :--- | :--- |
|  |  |  |

```text

```

