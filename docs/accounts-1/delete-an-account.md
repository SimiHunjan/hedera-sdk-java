# Delete an account

`AccountDeleteTransaction()` deletes an existing account from the Hedera network. Before deleting an account, the existing hbars must be transferred to another account. If you fail to transfer the hbars, you will receive an error message "setTransferAccountId\(\) required" Transfers cannot be made into a deleted account as the transaction will fail. A record of the deleted account will remain in the ledger until it expires.The expiration of a deleted account can be extended.

## Advanced

```java
new AccountDeleteTransaction()
.setTransferAccountId()
.setDeleteAccountId()
.setTransactionFee();
```

| Method | Type | Description | Default Value |
| :--- | :--- | :--- | :--- |
| **`setTransferAccountId()`** | `accountId` | The ID of the account the tinybars will be transferred to from the account that will be deleted. | None |
| **`setDeleteAccountId()`** |  |  | None |
|  |  |  | None |

##  Example

