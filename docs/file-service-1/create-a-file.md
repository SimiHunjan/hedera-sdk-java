# Create a file

`FileCreateTransaction()` creates a new file. The file is referenced by its file ID which can be obtained from the receipt or record of the transaction. The file does not have a file name. If the file is too big to create with a single `FileCreateTransaction()`, the file can be appended with the remaining content multiple times using the `FileAppendTransaction()` constructor.



| Constructor | Description |
| :--- | :--- |
| `FileCreateTransaction` | Initializes the FileCreateTransaction object |

```java
new FileCreateTransaction()
    .addKey()
    .setContents()
    .setExpirationTime()
    .setTransactionFee()
    .setMemo()
    .execute()

```

| Method | Type | Description |
| :--- | :--- | :--- |
| `addKey(<key>)` | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) | The public key of the owner of the file |
| `setContents(<contents>)` | bytes\[\] | The file contents |
| `setExpirationTime(<expiration>)` | Instant | The time at which this file should expire \(unless FileUpdateTransaction is used before then to extend its life\) |
| `setTransactionFee(<fee>)` | long | The fee for the transaction in tinybars |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |

## Example

```java
// The file is required to be a byte array,
// you can easily use the bytes of a file instead.
byte[] fileContents = "Hedera hashgraph is great!".getBytes();

TransactionId txId = new FileCreateTransaction()
     // Use the same key as the operator to "own" this file
     .addKey(OPERATOR_KEY.getPublicKey())
     .setContents(fileContents)
     // The default max fee of 1 HBAR is not enough to make a file ( starts around 1.1 HBAR )
     .setMaxTransactionFee(200_000_000) // 2 HBAR
     .execute(client);

TransactionReceipt receipt = txId.getReceipt(client);
FileId newFileId = receipt.getFileId();

System.out.println("file: " + newFileId);
```

