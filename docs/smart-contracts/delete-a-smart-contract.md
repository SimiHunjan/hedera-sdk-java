# Delete a smart contract

| Constructor | Description |
| :--- | :--- |
| `ContractDeleteTransaction()` | ​Initializes the ContractDeleteTransaction object |

```java
​new ContractDeleteTransaction()
    .setContractId()
    .setMaxTransactionFee()
    .setTransactionId()
    .setTransactionValidDuration()
    .setNodeAccountId()
    .setMemo()
    .sign()
    .build()
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
      <td style="text-align:left"><code>setContractId(&lt;contractID&gt;)</code>
      </td>
      <td style="text-align:left">ContractID</td>
      <td style="text-align:left">The ID of the contract</td>
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
      <td style="text-align:left"><code>setTransactionValidDuration(&lt;duration&gt;)</code>
      </td>
      <td style="text-align:left">Duration</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setNodeAccountId(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountID</td>
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
</table>‌

## Example <a id="example"></a>

```text
​
```

