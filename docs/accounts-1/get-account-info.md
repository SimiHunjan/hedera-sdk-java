# Get account info

`AccountInfoQuery()` returns all of the information about an account. This **does not** include the list of records associated with the account.

| Constructor | Description |
| :--- | :--- |
| `AccountInfoQuery()` |  |

```java
new AccountInfoQuery()
```

| Method | Type | Description |
| :--- | :--- | :--- |
| setAccountId\(&lt;accountId&gt;\) | AccountId | The accountId of the account to return the query for |

## Example

```java
new AccountInfoQuery()
.setAccountId()
.build()

```

