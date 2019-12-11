# Update an account

Update the properties of a Hedera account

`AccountUpdateTransaction()` updates/changes the properties for an existing account. Any null field is ignored \(left unchanged\). Any of the following properties can be updated for an account:

* Auto Renew Period
* Expiration Time
* Key\(s\)
* Send Record Threshold
* Receive Record Threshold 
* Proxy Account

{% hint style="danger" %}
The account must be signed by the **old key\(s\)** and **new key\(s\)** when updating the keys of an account.
{% endhint %}



## Advanced  <a id="advanced-methods-and-descriptions"></a>

```java
new AccountUpdateTransaction()
  .setAccountForUpdate()
  .setAutoRenewPeriod()
  .setExpirationTime()
  .setKey()
  .setSendRecordThreshold()
  .setReceiveRecordThreshold()
  .setProxyAccount()
  .setTransactionFee()
  .sign();
```



<table>
  <thead>
    <tr>
      <th style="text-align:left">Property</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setAccountForUpdate()</code>
      </td>
      <td style="text-align:left">accoountId</td>
      <td style="text-align:left">
        <p>The ID of the account to update in this transaction</p>
        <p><em>default:  None</em>
        </p>
        <p></p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewPeriod()</code>
      </td>
      <td style="text-align:left">duration</td>
      <td style="text-align:left">
        <p>The period of time in which the account will auto-renew in seconds. Duration
          type is in seconds. For example, one hour would result in the input value
          of <code>3600 </code>seconds</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setExpirationTime()</code>
      </td>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left">
        <p>The new expiration time to extend to.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setKey()</code>
      </td>
      <td style="text-align:left">key</td>
      <td style="text-align:left">
        <p>The public key generated for the new account.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setSendRecordThreshold()</code>
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
      <td style="text-align:left"><code>setReceiveRecordThreshold()</code>
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
      <td style="text-align:left"><code>setProxyAccount()</code>
      </td>
      <td style="text-align:left">accountId</td>
      <td style="text-align:left">
        <p>ID of account to which this account should be proxy staked.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTransactionFee()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>The transaction fee (node fee, service fee, and network fee combined)
          to process the transaction.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>sign()</code>
      </td>
      <td style="text-align:left">key</td>
      <td style="text-align:left">
        <p>The private key of the account executing and paying for the transaction.
          The transaction does not need to be explicitly signed if the signer is
          the operator.</p>
        <p><em>default:  None</em>
        </p>
      </td>
    </tr>
  </tbody>
</table>

## Update Account Keys Example:

The following example:

* Create a new account
* Update the keys of that account
* Validate the keys have been changed by requesting the account info

```java
public final class UpdateAccountPublicKey {

    // see `.env.sample` in the repository root for how to specify these values
    // or set environment variables with the same names
    private static final AccountId NODE_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("NODE_ID")));
    private static final String NODE_ADDRESS = Objects.requireNonNull(Dotenv.load().get("NODE_ADDRESS"));
    private static final AccountId OPERATOR_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_ID")));
    private static final Ed25519PrivateKey OPERATOR_KEY = Ed25519PrivateKey.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_KEY")));

    private UpdateAccountPublicKey() { }

    public static void main(String[] args) throws HederaException {
        // To improve responsiveness, you should specify multiple nodes using the
        // `Client(<Map<AccountId, String>>)` constructor instead
        Client client = new Client(NODE_ID, NODE_ADDRESS);

        // Defaults the operator account ID and key such that all generated transactions will be paid for
        // by this account and be signed by this key
        client.setOperator(OPERATOR_ID, OPERATOR_KEY);

        client.setMaxTransactionFee(800000000);

        // First, we create a new account so we don't affect our account

        Ed25519PrivateKey originalKey = Ed25519PrivateKey.generate();
        Transaction acctTransaction = new AccountCreateTransaction()
            .setMaxTransactionFee(1_000_000_000)
            .setKey(originalKey.getPublicKey())
            .setInitialBalance(100_000_000)
            .build(client);

        System.out.println("transaction ID: " + acctTransaction.execute(client));
        AccountId accountId = acctTransaction.getReceipt(client).getAccountId();
        System.out.println("account = " + accountId);
        // Next, we update the key

        Ed25519PrivateKey newKey = Ed25519PrivateKey.generate();

        System.out.println(" :: update public key of account " + accountId);
        System.out.println("set key = " + newKey.getPublicKey());

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
    }
}

```

