# Append to a file

`FileAppendTransaction()` appends content to the end of an existing file.

| Constructor | Description |
| :--- | :--- |
| `FileAppendTransaction()` | Initializes the FileAppendTransaction object |

```java
new FileAppendTransaction()
     .setFileId()
     .setContents()
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
      <td style="text-align:left">The <code>fileId</code> of the file to append content to</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setContents(&lt;content&gt;)</code>
      </td>
      <td style="text-align:left">byte[ ]</td>
      <td style="text-align:left">The appended content in byte format</td>
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

