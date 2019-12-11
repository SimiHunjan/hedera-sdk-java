# Get account claims

`AccountClaimQuery()` returns a single claim attached to the account. If there is no claim attached the account then the query will return null.

```java
new AccountClaimQuery()
  .setAccount()
  .setHash()
  .build();
```

## Example

