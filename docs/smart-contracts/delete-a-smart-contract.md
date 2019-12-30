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
| `setContractId(<contractID>)` | ContractID | The ID of the contract |
| `setMaxTransactionFee(<fee>)` | long | The maximum fee to be paid for this transaction executed by this client. The actual fee may be less, but will never be greater than this value. |
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

