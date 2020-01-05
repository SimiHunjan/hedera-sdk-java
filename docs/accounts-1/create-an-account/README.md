---
description: AccountCreateTransaction
---

# Create an account

The account represents your account specific to the Hedera network. Accounts are required to utilize the Hedera network services and to pay network transaction fees. 

{% hint style="info" %}
When creating a **new account** an existing account will need to fund the initial balance and pay for the transaction fee.
{% endhint %}

| Constructor | Description |
| :--- | :--- |
| `AccountCreateTransaction()` | Initializes the AccountCreateTransaction object |

## Basic

```java
new AccountCreateTransaction()
  .setKey()
  .setInitialBalance()
  .setMaxTransactionFee()
  .build();
```

### 

| Methods | Type | Description |
| :--- | :---: | :--- |
| `setKey(<key>)` | Ed25519PrivateKey | The private key generated for the new account. |
| `setInitialBalance(<amount>)` | uint64 | The initial balance for the account in tinybars |

### Example:

```java
Transaction tx = new AccountCreateTransaction()
     // The only _required_ property here is `key`
     .setKey(newKey.getPublicKey())
     .setInitialBalance(1000)
     .setMaxTransactionFee(10000000)
     .build(client);

tx.execute(client);

// This will wait for the receipt to become available
TransactionReceipt receipt = tx.getReceipt(client);

AccountId newAccountId = receipt.getAccountId();

System.out.println("account = " + newAccountId);
```

## Advanced

```java
new AccountCreateTransaction()
  .setKey()
  .setInitialBalance()
  .setMaxTransactionFee()
  .setAutoRenewPeriod()
  .setReceiverSignatureRequired()
  .setReceiveRecordThreshold()
  .setSendRecordThreshold()
  .setMemo()
  .setRealmId()
  .setShardId()
  .setProxyAccountId()
  .setTransactionId()
  .setNewRealmAdminKey()
  .build();
```



<table>
  <thead>
    <tr>
      <th style="text-align:left">Methods</th>
      <th style="text-align:center">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setMaxTransactionFee(&lt;fee&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">The maximum fee to be paid for this transaction executed by this client.
        The actual fee may be less, but will never be greater than this value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewPeriod(&lt;autoRenewPeriod&gt;)</code>
      </td>
      <td style="text-align:center">Duration</td>
      <td style="text-align:left">
        <p>The period of time in which the account will auto-renew in seconds. The
          account is charged tinybars for every auto-renew period. Duration type
          is in seconds. For example, one hour would result in the input value of
          3,600 seconds.NOTE: This is fixed to approximately 3 months (7890000 seconds).
          Any other value will return the following error: AUTORENEW_DURATION_NOT_IN_RANGE.</p>
        <p><em>default: 2,592,000 seconds</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setReceiverSignatureRequired(&lt;boolean&gt;)</code>
      </td>
      <td style="text-align:center">boolean</td>
      <td style="text-align:left">
        <p>If true, all the account keys must sign any transaction depositing into
          this account (in addition to all withdrawals)</p>
        <p><em>default: false</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setReceiveRecordThreshold(&lt;receiveRecordThreshold&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">Creates a record for any transaction that deposits more than x value of
        tinybars.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setSendRecordThreshold(&lt;sendRecordThreshold&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">Creates a record for any transaction that withdraws more than x value
        of tinybars.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMemo()</code>
      </td>
      <td style="text-align:center">String</td>
      <td style="text-align:left">Any notes or descriptions that should be put into the record (max length
        100)</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setRealmId(&lt;realmId&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">The ID of the realm</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setShardId(&lt;shardId&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">The ID of the shard</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTransactionId(&lt;transactionId&gt;)</code>
      </td>
      <td style="text-align:center">TransactionId</td>
      <td style="text-align:left">The ID of the transaction</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setNewRealAdminKey(&lt;publicKey&gt;)</code>
      </td>
      <td style="text-align:center">PublicKey</td>
      <td style="text-align:left">if realmID is null, then this the admin key for the new realm that will
        be created</td>
    </tr>
  </tbody>
</table>