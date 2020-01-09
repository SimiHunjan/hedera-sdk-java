# Get account info

`AccountInfoQuery()` returns all of the information about an account. This **does not** include the list of records associated with the account.

This information includes:

* Account ID
* Key\(s\)
* Balance
* Expiration time
* AutoRenewPeriod
* Whether the account is deleted or not
* Whether the receiver signature is required or not
* The proxy account ID, if any

| Constructor | Description |
| :--- | :--- |
| `AccountInfoQuery()` | Initializes the AccountInfoQuery object |

```java
new AccountInfoQuery()
     .setAccountId()
     .setMaxQueryPayment()
     .execute();
```

| Method | Type | Description |
| :--- | :--- | :--- |
| `setAccountId(<accountId>)` | AccountId | The accountId of the account to return the information for |
| `setMaxQueryPayment(<maxPayment>)` | long | The max the client will pay for the query |
| `getCost(<client>)` | Client | Returns the cost of the query  |

## Example

```java
Transaction transaction = new AccountUpdateTransaction()
     .setAccountForUpdate(accountId)
     .setKey(newKey.getPublicKey())
     // Sign with the previous key and the new key
     .build(client)
     .sign(originalKey)
     .sign(newKey);

System.out.println("transaction ID: " + transaction.id);

transaction.execute(client);
// (important!) wait for the transaction to complete by querying the receipt
transaction.getReceipt(client);

// Now we fetch the account information to check if the key was changed
System.out.println(" :: getAccount and check our current key");

AccountInfo info = client.getAccount(accountId);

System.out.println("key = " + info.key);
```

