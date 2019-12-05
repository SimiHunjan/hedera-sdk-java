# Update an account

Update the properties of a Hedera account

`AccountUpdateTransaction()` updates/changes the properties for an existing account. Any null field is ignored \(left unchanged\).

The account must be signed by the **old keys** and **new key** when updating the keys of an account.

## Advanced Methods and Descriptions <a id="advanced-methods-and-descriptions"></a>

```java
new AccountUpdateTransaction()
  .setAccountForUpdate()
  .setAutoRenewPeriod()
  .setExpirationTime()
  .setKey()
  .setSendRecordThreshold()
  .setReceiveRecordThreshold()
  .setProxyAccount()
  .seTransactionFee()
  .sign();
```

