# Append to a file

`FileAppendTransaction()` appends content to the end of an existing file.

### Constructor

| Constructor | Description |
| :--- | :--- |
| `FileAppendTransaction()` | Initializes the FileAppendTransaction object |

### Methods

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setFileId(<fileId>)` | FileId | The `fileId` of the file to append content to |
| `setContents(<content>)` | byte\[ \] | The appended content in byte format |
| `setMaxTransactionFee(<fee>)` | long | The maximum fee to be paid for this transaction executed by this client. The actual fee may be less, but will never be greater than this value. |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |

## Example

```java

```

