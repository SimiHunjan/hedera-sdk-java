# Create an account

The account represents your account specific to the Hedera network. Accounts are required to utilize the Hedera network services and to pay network transaction fees. Hedera account IDs have the format: x.y.z. eg 0.0.3. where:

* x represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard
* y represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* z represents the account number \( `accountId` \)

Together these values make up your accountId. When an accountId is requested, be sure all three values are included.

## Basic

The easiest way to create an account is using `.createAccount()`. with the simple client. `createAccount()` requires two properties, the public key to be associated with the new account and the initial balance in tinybars.

```java
client.setMaxTransactionFee().createAccount(PublicKey, initialBalance);
```

## Advanced

Additional properties can be set when creating a new account. The properties and their descriptions can be found below.

```java
new AccountCreateTransaction()
  .setKey()
  .setInitialBalance()
  .setTransactionfee()
  .setAutoRenewPeriod()
  .setReceiverSignatureRequired()
  .setReceiveRecordThreshold()
  .setSendRecordThreshold();
```

### Descriptions

| Property                         | Type     | Description                                                                                                                                                                                                                                                                                                                                                                             | Default Value     |
|----------------------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| `setKey()`                       | key      | The private key generated for the new account.                                                                                                                                                                                                                                                                                                                                          | None              |
| `setInitialBalance()`            | uint64   | The initial balance for the account in tinybars                                                                                                                                                                                                                                                                                                                                         | None              |
| `setTransactionFee()`            | duration | The transaction fee for the account create transaction                                                                                                                                                                                                                                                                                                                                  | None              |
| `setAutoRenewPeriod()`           | long     | The period of time in which the account will auto-renew in seconds. The account is charged tinybars for every auto-renew period. Duration type is in seconds. For example, one hour would result in the input value of 3,600 seconds.NOTE: This is fixed to approximately 3 months (7890000 seconds). Any other value will return the following error: AUTORENEW_DURATION_NOT_IN_RANGE. | 2,592,000 seconds |
| `setReceiverSignatureRequired()` | boolean  |                                                                                                                                                                                                                                                                                                                                                                                   | False             |




