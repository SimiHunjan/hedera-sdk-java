# Get file contents

`FileContentsQuery()` returns the contents of a file. If the file is empty the content field is empty. The response returns the file ID and the file contents in bytes.

| Constructor | Description |
| :--- | :--- |
| `FileContentsQuery()` | Initializes a FileContentQuery object |

```java
new FileContentsQuery()
    .setAcountId()
    .execute();

```

| Method | Type | Description |
| :--- | :--- | :--- |
| `setAccountId(<account>)` | AccountID | The ID of the file to get contents from |

## Example

```java
byte[] fileContents = ("Hedera is great!").getBytes();

// Create the new file and set its properties
TransactionId newFileTxId = new FileCreateTransaction()
    .addKey(OPERATOR_KEY.getPublicKey()) // The public key of the owner of the file
    .setContents(fileContents) // Contents of the file
    .setMaxTransactionFee(200_000_000L) // 2h
    .execute(client);

FileId newFileId = newFileTxId.getReceipt(client).getFileId();

//Print the file ID to console
System.out.println("The new file ID is " + newFileId.toString());

// Get file contents
FileGetContentsResponse contents = new FileContentsQuery()
    .setFileId(newFileId)
    .execute(client);

// Prints query results to console
System.out.println("File content query results: " + contents.getFileContents().getContents().toStringUtf8());
```

