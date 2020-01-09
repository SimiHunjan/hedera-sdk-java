# Get account balance

## Basic

The example below uses the client object and calls the `getAccountBalance` method to return the balance of account.

| Method | Type | Description |
| :--- | :--- | :--- |
| `getAccountBalance(<accountId>)` | [AccountId](../../user-defined-data-types.md#accountid) | Get the balance of an account |

### Example

```java
AccountId operatorId = ExampleHelper.getOperatorId();
Client client = ExampleHelper.createHederaClient();
long balance = client.getAccountBalance(operatorId);

System.out.println("balance = " + balance);


TransactionId transactionId = new TransactionId(operatorId);
System.out.println(transactionId);
```

## Advanced 

| Constructor | Description |
| :--- | :--- |
| `AccountBalanceQuery()` | Initializes the AccountBalanceQuery object |

| Method | Type | Description |
| :--- | :--- | :--- |
| `setAccountId(<account>)` | [AccountId](../../user-defined-data-types.md#accountid) | The accountId of the account to retrieve the balance for |

## Example

```java
Long balance = new AccountBalanceQuery()
     .setAccountId(OPERATOR_ID)
     .execute(client);

System.out.println("balance = " + balance);
```

