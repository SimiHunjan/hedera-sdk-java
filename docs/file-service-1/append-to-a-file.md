# Append to a file

`FileAppendTransaction()` appends content to the end of an existing file.

| Constructor | Description |
| :--- | :--- |
| `FileAppendTransaction()` | Initializes the FileAppendTransaction object |

| Method | Type | Description |
| :--- | :--- | :--- |
| `setFileId(<fileId>)` | FileId | The `fileId` of the file to append content to |
| `setContents(<content>)` | byte\[ \] | The appended content in byte format |
| `setTransactionFee(<fee>)` | long | The fee for the transaction in tinybars |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |

## Example

```java

```

