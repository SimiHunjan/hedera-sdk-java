---
description: AccountDeleteTransaction
---

# Delete an account

`AccountDeleteTransaction()` deletes an existing account from the Hedera network. Before deleting an account, the existing hbars must be transferred to another account. If you fail to transfer the hbars, you will receive an error message "setTransferAccountId\(\) required." Transfers cannot be made into a deleted account. A record of the deleted account will remain in the ledger until it expires.The expiration of a deleted account can be extended.

## Basic

| Constructor | Description |
| :--- | :--- |
| `AccountDeleteTransaction()` | Initializes the AccountDeleteTransaction object |

```java
new AccountDeleteTransaction()
.setTransferAccountId()
.setDeleteAccountId()
.setTransactionFee()
.setMemo()
.build();
```

| Method | Type | Description |
| :--- | :--- | :--- |
| `setTransferAccountId(<accountId>)` | [AccountId](../user-defined-data-types.md#accountid) | The ID of the account the tinybars will be transferred to from the account that will be deleted |
| `setDeleteAccountId(<accountId>)` | [AccountId](../user-defined-data-types.md#accountid) | The ID of the account to be deleted from the Hedera network |
| `setTransactionFee(<fee>)` | long | The fee for the transaction in tinybars |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |

###  Example

```java

```

## Advanced

| Methods | Type | Description |
| :--- | :--- | :--- |
|  |  |  |



