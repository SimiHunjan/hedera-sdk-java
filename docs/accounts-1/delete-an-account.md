---
description: AccountDeleteTransaction
---

# Delete an account

`AccountDeleteTransaction()` deletes an existing account from the Hedera network. Before deleting an account, the existing hbars must be transferred to another account. If you fail to transfer the hbars, you will receive an error message "setTransferAccountId\(\) required." Transfers cannot be made into a deleted account. A record of the deleted account will remain in the ledger until it expires.The expiration of a deleted account can be extended.

| Constructor | Description |
| :--- | :--- |
| `AccountDeleteTransaction()` | Constructs the account delete object |

```java
new AccountDeleteTransaction()
.setTransferAccountId()
.setDeleteAccountId()
.build();
```

| Method | Type | Description |
| :--- | :--- | :--- |
| `setTransferAccountId(<accountId>)` | [AccountId](../user-defined-data-types.md#accountid) | The ID of the account the tinybars will be transferred to from the account that will be deleted |
| `setDeleteAccountId(<accountId>)` | [AccountId](../user-defined-data-types.md#accountid) | The ID of the account to be deleted from the Hedera network |

##  Example

```java
Transaction transaction = new AccountDeleteTransaction()
.setTransferAccountId(accountId)
.setDeleteAccountId(deleteAccountId)
.build(client);
```

