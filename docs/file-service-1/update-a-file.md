# Update a file

`FileUpdateTransaction()` updates the metadata for a file. This transaction must be signed by all the keys assigned to the file.

| Constructor | Description |
| :--- | :--- |
| `FileUpdateTransaction()` | Intializes the FileUpdateTransaction object |

| Method | Type | Description |
| :--- | :--- | :--- |
| `setFileId(<fileId>)` | FileId | The FileID of the file to update |
| `addKey(<key>)` | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) | The public key\(s\) to add to update the file with |
| `setContents(<contents>)` | byte\[ \] | The contents to update the file with |
| `setExpirationTime(<expiration>)` | Instant | The expiration time to update the file |
| `setMaxTransactionFee(<fee>)` | long | The maximum fee to be paid for this transaction executed by this client. The actual fee may be less, but will never be greater than this value. |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |

## Example

```java

```

