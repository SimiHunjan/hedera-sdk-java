# Delete a file

`FileDeleteTransaction()` deletes a file stored on the Hedera network. Once the file has been deleted, it will be marked as deleted until it expires and will not retain any of its contents.

| Constructor | Description |
| :--- | :--- |
| `FileDeleteTransaction()` | Initializes the FileDeleteTransaction object |

```java
new FileDeleteTransaction()
     .setFileId()
     .setMaxTransactionFee()
     .setTransactionId()
     .setNodeAccountId()
     .setTransactionValidDuration()
     .setMemo()
     .sign()
     .execute();

```

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setFileId(&lt;fileId&gt;)</code>
      </td>
      <td style="text-align:left">FileId</td>
      <td style="text-align:left">The ID of the file to delete</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMaxTransactionFee(&lt;fee&gt;)</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">The maximum fee to be paid for this transaction executed by this client.
        The actual fee may be less, but will never be greater than this value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTransactionId(&lt;transactionId&gt;)</code>
      </td>
      <td style="text-align:left">TransactionID</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setNodeAccountId(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountID</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTransactionValidDuration(&lt;duration&gt;)</code>
      </td>
      <td style="text-align:left">Duration</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMemo(&lt;memo&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>A short note attached to the transaction</p>
        <p>Max: 100 bytes</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>sign(&lt;key&gt;)</code>
      </td>
      <td style="text-align:left">PrivateKey</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>## Example

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

