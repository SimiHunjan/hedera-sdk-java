# Get account balance

## Basic

The example below uses the client object and calls the `getAccountBalance` method to return the balance of account.

| Method | Type | Description |
| :--- | :--- | :--- |
| `getAccountBalance(<accountId>)` | [AccountId](../../user-defined-data-types.md#accountid) | Get the balance of an account |

```java
AccountId operatorId = ExampleHelper.getOperatorId();
Client client = ExampleHelper.createHederaClient();
long balance = client.getAccountBalance(operatorId);

System.out.println("balance = " + balance);


TransactionId transactionId = new TransactionId(operatorId);
System.out.println(transactionId);
```

## Advanced 

| Constructor | Type | Description |
| :--- | :--- | :--- |
| `AccountBalanceQuery(<client>)` | Client | Initializes the AccountBalanceQuery object |

```java
new AccountBalanceQuery();
```

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setAccountId(<accountId>)` | AccountId | The account ID of the account to return the balance for |

### Example

```java
AccountId operatorId = ExampleHelper.getOperatorId();
Client client = ExampleHelper.createHederaClient();

AccountBalanceQuery query = new AccountBalanceQuery(client).setAccountId(operatorId);

Long balance = query.execute();

System.out.println("balance = " + balance);
```

