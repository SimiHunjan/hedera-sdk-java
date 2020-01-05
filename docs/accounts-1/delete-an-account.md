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

| Method | Type | Description |
| :--- | :--- | :--- |
| `setTransferAccountId(<accountId>)` | [AccountId](../user-defined-data-types.md#accountid) | The ID of the account the tinybars will be transferred to from the account that will be deleted |
| `setDeleteAccountId(<accountId>)` | [AccountId](../user-defined-data-types.md#accountid) | The ID of the account to be deleted from the Hedera network |
| `setMaxTransactionFee(<fee>)` | long | The maximum fee to be paid for this transaction executed by this client. The actual fee may be less, but will never be greater than this value. |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |

##  Example

```java
// To improve responsiveness, you should specify multiple nodes using the
// `Client(<Map<AccountId, String>>)` constructor instead
Client client = new Client(NODE_ID, NODE_ADDRESS);

// Defaults the operator account ID and key such that all generated transactions will be paid for
// by this account and be signed by this key
client.setOperator(OPERATOR_ID, OPERATOR_KEY);

Ed25519PrivateKey newKey = Ed25519PrivateKey.generate();
Ed25519PublicKey pubKey = newKey.getPublicKey();

TransactionId txId = new AccountCreateTransaction()
    // The only _required_ property here is `key`
    .setKey(newKey.getPublicKey())
    .setInitialBalance(900000000)
    .execute(client);

TransactionReceipt receipt = txId.getReceipt(client);

AccountId accountId = receipt.getAccountId();

System.out.println(accountId);

TransactionId deleteAccount = new AccountDeleteTransaction()
    .setTransferAccountId(OPERATOR_ID)
    .setDeleteAccountId(accountId)
    // Have to sign with the private key of the account being deleted 
    .execute(client.setOperator(accountId,newKey));


System.out.println(deleteAccount.getReceipt(client).status);

// Update operator to an exisitng account
client.setOperator(OPERATOR_ID,OPERATOR_KEY);

AccountInfo accountInfo = new AccountInfoQuery()
    .setAccountId(accountId)
    .setPaymentAmount(200_000_000)
    .execute(client);

```

## Advanced

