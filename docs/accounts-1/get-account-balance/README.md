# Get account balance

## Basic

You can quickly obtain an account balance by invoking the `getAccountBalance()` method on the [client ](../../client.md)object.

| Method | Type | Description |
| :--- | :--- | :--- |
| `getAccountBalance(<accountId>)` | [AccountId](../../user-defined-data-types.md#accountid) | Get the balance of an account |

```java
long balance = client.getAccountBalance(OPERATOR_ID);
System.out.println("balance = " + balance);
```

## Advanced

You can also construct an `AccountBalanceQuery()` object.

| Constructor | Description |
| :--- | :--- |
| `AccountBalanceQuery()` | Initializes the AccountBalanceQuery object |

```java
new AccountBalanceQuery()
.setAccountId()
.execute();
```

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

