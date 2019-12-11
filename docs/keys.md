---
description: Generate keys using Java SDK
---

# Generate Keys

## Ed25519 Key Pair

| **Method** | **Description** | Reference |
| :--- | :--- | :--- |
| **`Ed25519PrivateKey.generate()`** | Generates a Ed25519 private key | [Ed25519PrivateKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PrivateKey.java) |
| **`<newKey>.getPublicKey()`** | Gets the corresponding public key to the previously generated private key | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) |

### Example:

```java
// Generate a Ed25519 private, public key pair
Ed25519PrivateKey newKey = Ed25519PrivateKey.generate();
Ed25519PublicKey newPublicKey = newKey.getPublicKey();

System.out.println("private key = " + newKey);
System.out.println("public key = " + newPublicKey);
```

