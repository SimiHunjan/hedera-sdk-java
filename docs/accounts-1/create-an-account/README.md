---
description: AccountCreateTransaction
---

# Create an account

The account represents your account specific to the Hedera network. Accounts are required to utilize the Hedera network services and to pay network transaction fees. 

{% hint style="info" %}
When creating a **new account** an existing account will need to fund the initial balance and pay for the transaction fee.
{% endhint %}

## Basic

```java
Client client = ExampleHelper.createHederaClient();
```

## Advanced

| Constructor | Description |
| :--- | :--- |
| `AccountCreateTransaction()` | Initializes the AccountCreateTransaction object |

```java
new AccountCreateTransaction()
  .setKey()
  .setInitialBalance()
  .setTransactionFee()
  .setAutoRenewPeriod()
  .setReceiverSignatureRequired()
  .setReceiveRecordThreshold()
  .setSendRecordThreshold()
  .setMemo()
  .setRealmId()
  .setShardId()
  .setProxyAccountId()
  .setTransactionId()
  .setNodeAccountId()
  .setNewRealmAdminKey()
  .setGenerateRecord()
  .build();
```

### 

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
      <td style="text-align:left"><code>setKey(&lt;key&gt;)</code>
      </td>
      <td style="text-align:center">Ed25519PrivateKey</td>
      <td style="text-align:left">The private key generated for the new account.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setInitialBalance(&lt;amount&gt;)</code>
      </td>
      <td style="text-align:center">uint64</td>
      <td style="text-align:left">The initial balance for the account in tinybars</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTransactionFee(&lt;fee&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">The fee for the transaction</td>
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
      <td style="text-align:left"><code>setNodeAccountId(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:center">AccountId</td>
      <td style="text-align:left">The node that will submit the transaction to the Hedera network</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setNewRealAdminKey(&lt;publicKey&gt;)</code>
      </td>
      <td style="text-align:center">PublicKey</td>
      <td style="text-align:left">if realmID is null, then this the admin key for the new realm that will
        be created</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setGenerateRecord(&lt;generateRecord&gt;)</code>
      </td>
      <td style="text-align:center">boolean</td>
      <td style="text-align:left">Whether a record should be generated for the transaction or not</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>executeForReceipt()</code>
      </td>
      <td style="text-align:center">TransactionReceipt</td>
      <td style="text-align:left">Returns the receipt for the transaction</td>
    </tr>
  </tbody>
</table>### Example:

```java
AccountCreateTransaction tx = new AccountCreateTransaction(client)
    // The only _required_ property here is `key`
    .setKey(newKey.getPublicKey())
    .setInitialBalance(1000)
    .setTransactionFee(10_000_000);

// This will wait for the receipt to become available
TransactionReceipt receipt = tx.executeForReceipt();

AccountId newAccountId = receipt.getAccountId();

System.out.println("account = " + newAccountId);
```



