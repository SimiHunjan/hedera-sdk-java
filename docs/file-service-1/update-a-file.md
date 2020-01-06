# Update a file

`FileUpdateTransaction()` updates the metadata for a file. This transaction must be signed by all the keys assigned to the file.

| Constructor | Description |
| :--- | :--- |
| `FileUpdateTransaction()` | Intializes the FileUpdateTransaction object |

```java
new FileUpdateTransaction()
    .setFileId()
    .addKey()
    .setContents()
    .setExpirationTime()
    .setMaxTransactionFee()
    .setMemo()
    .build();
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
      <td style="text-align:left">The FileID of the file to update</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addKey(&lt;key&gt;)</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java">Ed25519PublicKey</a>
      </td>
      <td style="text-align:left">The public key(s) to add to update the file with</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setContents(&lt;contents&gt;)</code>
      </td>
      <td style="text-align:left">byte[ ]</td>
      <td style="text-align:left">The contents to update the file with</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setExpirationTime(&lt;expiration&gt;)</code>
      </td>
      <td style="text-align:left">Instant</td>
      <td style="text-align:left">The expiration time to update the file</td>
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

```

