# Get account balance

`AccountBalanceQuery()` returns the account balance. The account is charged tinybars each time the request is executed.

You can quickly obtain the account balance by invoking the getAccountBalance\(\) method on the client object.

| Method | Type | Description |
| :--- | :--- | :--- |
| &lt;client&gt;.getAccountBalance\(&lt;accountId&gt;\) | AccountId | Get the balance of an account |

```java
long balance = client.getAccountBalance(OPERATOR_ID);
System.out.println("balance = " + balance);
```

| Constructor | Description |
| :--- | :--- |
| new AccountBalanceQuery\(\) | Instantiates an account balance query object |

| Method | Type | Description |
| :--- | :--- | :--- |
| setAccountId\(&lt;accountId&gt;\) | AccountId | The accountId of the account to retrieve the balance for |

## Example

```java
Long balance = new AccountBalanceQuery()
     .setAccountId(OPERATOR_ID)
     .execute(client);

System.out.println("balance = " + balance);
```



