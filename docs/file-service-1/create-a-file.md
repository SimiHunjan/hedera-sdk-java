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
    .setMaxTransactionFee()
    .setMemo()
    .execute()

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
      <td style="text-align:left"><code>addKey(&lt;key&gt;)</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java">Ed25519PublicKey</a>
      </td>
      <td style="text-align:left">The public key of the owner of the file</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setContents(&lt;contents&gt;)</code>
      </td>
      <td style="text-align:left">bytes[]</td>
      <td style="text-align:left">The file contents</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setExpirationTime(&lt;expiration&gt;)</code>
      </td>
      <td style="text-align:left">Instant</td>
      <td style="text-align:left">The time at which this file should expire (unless FileUpdateTransaction
        is used before then to extend its life)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMaxTransactionFee(&lt;fee&gt;)</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">The maximum fee to be paid for this transaction executed by this client.
        The actual fee may be less, but will never be greater than this value.</td>
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
  </tbody>
</table>## Example

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

