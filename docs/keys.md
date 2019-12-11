---
description: Generate keys using Java SDK
---

# Generate Keys

| **Method** | **Description** |
| :--- | :--- |
| **`Ed25519PrivateKey.generate()`** | Generates a Ed25519 private key |
| **`Ed25519PrivateKey.generate().getPublicKey()`** | Gets the corresponding public key |

### Example:

```java
// Generate a Ed25519 private, public key pair
Ed25519PrivateKey newKey = Ed25519PrivateKey.generate();
Ed25519PublicKey newPublicKey = newKey.getPublicKey();

System.out.println("private key = " + newKey);
System.out.println("public key = " + newPublicKey);
```

