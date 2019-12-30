# Advanced account balance

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

