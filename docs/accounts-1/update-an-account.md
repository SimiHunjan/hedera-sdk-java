---
description: AccountUpdateTransaction
---

# Update an account

`AccountUpdateTransaction()` updates/changes the properties for an existing account. Any null field is ignored \(left unchanged\). Any of the following properties can be updated for an account:

* Key\(s\)
* Auto Renew Period
* Expiration Time
* Send Record Threshold
* Receive Record Threshold 
* Proxy Account

{% hint style="danger" %}
The account must be signed by the **old key\(s\)** and **new key\(s\)** when updating the keys of an account.
{% endhint %}

| Constructor | Description |
| :--- | :--- |
| `AccountUpdateTransaction()` | Initializes the AccountUpdateTransaction object |

```java
new AccountUpdateTransaction()
  .setAccountForUpdate()
  .setKey()
  .setAutoRenewPeriod()
  .setExpirationTime()
  .setSendRecordThreshold()
  .setReceiveRecordThreshold()
  .setMaxTransactionFee()
  .setProxyAccount()
  .setMemo()
  .build();
```



<table>
  <thead>
    <tr>
      <th style="text-align:left">Methods</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setAccountForUpdate(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountId</td>
      <td style="text-align:left">
        <p>The ID of the account to update in this transaction</p>
        <p><em>default:  None</em>
        </p>
        <p></p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setKey(&lt;key&gt;)</code>
      </td>
      <td style="text-align:left">Ed25519PublicKey</td>
      <td style="text-align:left">
        <p>The public key generated for the new account.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewPeriod(&lt;autoRenewPeriod&gt;)</code>
      </td>
      <td style="text-align:left">Duration</td>
      <td style="text-align:left">
        <p>The period of time in which the account will auto-renew in seconds. Duration
          type is in seconds. For example, one hour would result in the input value
          of <code>3600 </code>seconds</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setExpirationTime(&lt;expirationTime&gt;)</code>
      </td>
      <td style="text-align:left">Instant</td>
      <td style="text-align:left">
        <p>The new expiration time to extend to.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setSendRecordThreshold(&lt;sendRecordThreshold&gt;)</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>Creates a record for any transaction that withdraws more than x value
          of tinybars.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setReceiveRecordThreshold(&lt;receiveRecordThreshold)</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>Creates a record for any transaction that deposits more than x value of
          tinybars.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMaxTransactionFee(&lt;fee&gt;)</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">The maximum fee to be paid for this transaction executed by this client.
        The actual fee may be less, but will never be greater than this value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setProxyAccount(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountId</td>
      <td style="text-align:left">
        <p>ID of account to which this account should be proxy staked.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMemo(&lt;memo&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Any notes or descriptions that should be put into the record (max length
        100)</td>
    </tr>
  </tbody>
</table>

### Example:

```java
Transaction transaction = new AccountUpdateTransaction()
     .setAccountForUpdate(accountId)
     .setKey(newKey.getPublicKey())
     // Sign with the previous key and the new key
     .build(client)
     .sign(originalKey)
     .sign(newKey);

System.out.println("transaction ID: " + transaction.id);

transaction.execute(client);
// (important!) wait for the transaction to complete by querying the receipt
transaction.getReceipt(client);

// Now we fetch the account information to check if the key was changed
System.out.println(" :: getAccount and check our current key");

AccountInfo info = client.getAccount(accountId);

System.out.println("key = " + info.key);
```

