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

| Method | Type | Description |
| :--- | :--- | :--- |
| `setContractId(<contractID>)` | ContractID |  |
| `setMaxTransactionFee(<fee>)` | long |  |
| `setTransactionId(<transactionId>)` | TransactionID |  |
| `setTransactionValidDuration(<duration>)` | Duration |  |
| `setNodeAccountId(<accountId>)` | AccountID |  |
| `setMemo(<memo>)` | String |  |
| `sign(<key>)` | PrivateKey |  |

‌

## Example <a id="example"></a>

```text
​
```

