---
description: AccountDeleteTransaction
---

# Delete an account

`AccountDeleteTransaction()` deletes an existing account from the Hedera network. Before deleting an account, the existing hbars must be transferred to another account. If you fail to transfer the hbars, you will receive an error message "setTransferAccountId\(\) required." Transfers cannot be made into a deleted account. A record of the deleted account will remain in the ledger until it expires.The expiration of a deleted account can be extended.

| Constructor | Description |
| :--- | :--- |
| `AccountDeleteTransaction()` | Initializes the AccountDeleteTransaction object |

```java
new AccountDeleteTransaction()
.setTransferAccountId()
.setDeleteAccountId()
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
      <td style="text-align:left"><code>setTransferAccountId(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left"><a href="../user-defined-data-types.md#accountid">AccountId</a>
      </td>
      <td style="text-align:left">The ID of the account the tinybars will be transferred to from the account
        that will be deleted</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setDeleteAccountId(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left"><a href="../user-defined-data-types.md#accountid">AccountId</a>
      </td>
      <td style="text-align:left">The ID of the account to be deleted from the Hedera network</td>
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
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>A short note attached to the transaction</p>
        <p>Max: 100 bytes</p>
      </td>
    </tr>
  </tbody>
</table>##  Example

```java
Transaction transaction = new AccountDeleteTransaction()
.setTransferAccountId(accountId)
.setDeleteAccountId(deleteAccountId)
.build(client);
```

