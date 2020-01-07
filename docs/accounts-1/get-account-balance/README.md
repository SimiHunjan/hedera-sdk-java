# Get account balance

You can quickly obtain an account balance by invoking the `getAccountBalance()` method on the [client ](../../client.md)object.

| Method | Type | Description |
| :--- | :--- | :--- |
| `getAccountBalance(<accountId>)` | [AccountId](../../user-defined-data-types.md#accountid) | Get the balance of an account |

```java
long balance = client.getAccountBalance(OPERATOR_ID);
System.out.println("balance = " + balance);
```

