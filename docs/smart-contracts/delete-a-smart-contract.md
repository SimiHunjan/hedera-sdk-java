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

```java
// create the contract's bytecode file
TransactionId fileTxId = new FileCreateTransaction().setExpirationTime(
    Instant.now()
        .plus(Duration.ofSeconds(3600)))
    // Use the same key as the operator to "own" this file
    .addKey(OPERATOR_KEY.getPublicKey())
    .setContents(byteCodeHex.getBytes())
    .execute(client);

TransactionReceipt fileReceipt = fileTxId.getReceipt(client);
FileId newFileId = fileReceipt.getFileId();

System.out.println("contract bytecode file: " + newFileId);

// create the contract itself
TransactionId contractTxId = new ContractCreateTransaction()
    .setAutoRenewPeriod(Duration.ofHours(1))
    .setGas(217000)
    .setBytecodeFile(newFileId)
    // set an admin key so we can delete the contract later
    .setAdminKey(OPERATOR_KEY.getPublicKey())
    .execute(client);

TransactionReceipt contractReceipt = contractTxId.getReceipt(client);

System.out.println(contractReceipt.toProto());

ContractId newContractId = contractReceipt.getContractId();

System.out.println("new contract ID: " + newContractId);

// now delete the contract
TransactionId contractDeleteTxnId = new ContractDeleteTransaction()
    .setContractId(newContractId)
    .execute(client);

TransactionReceipt contractDeleteResult = contractDeleteTxnId.getReceipt(client);

if (contractDeleteResult.getStatus() != ResponseCodeEnum.SUCCESS) {
    System.out.println("error deleting contract: " + contractDeleteResult.getStatus());
    return;
}
System.out.println("Contract successfully deleted");

```

