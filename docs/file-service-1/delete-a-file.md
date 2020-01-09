# Delete a file

`FileDeleteTransaction()` deletes a file stored on the Hedera network. Once the file has been deleted, it will be marked as deleted until it expires and will not retain any of its contents.

### Constructor

| Constructor | Description |
| :--- | :--- |
| `FileDeleteTransaction()` | Initializes the FileDeleteTransaction object |

### Methods

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setFileId(<fileId>)` | FileId | The ID of the file to delete |
| `setMaxTransactionFee(<fee>)` | long | The maximum fee to be paid for this transaction executed by this client. The actual fee may be less, but will never be greater than this value. |
| `setTransactionId(<transactionId>)` | TransactionID |  |
| `setNodeAccountId(<accountId>)` | AccountID |  |
| `setTransactionValidDuration(<duration>)` | Duration |  |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |
| `sign(<key>)` | PrivateKey |  |

## Example

```java
TransactionId fileDeleteTxnId = new FileDeleteTransaction()
     .setFileId(newFileId)
     .execute(client);

// if this doesn't throw then the transaction was a success
fileDeleteTxnId.getReceipt(client);

System.out.println("File deleted successfully.");

FileInfo fileInfo = new FileInfoQuery()
     .setFileId(newFileId)
     .execute(client);
```

