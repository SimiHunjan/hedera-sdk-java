---
description: CryptoTransferTransaction
---

# Transfer cryptocurrency

`CryptoTransferTransaction()` transfers tinybars from one Hedera account to different Hedera account in the Hedera network. The amount is in **tinybars** \(not hbars\). The transaction must be signed by all the keys from all sender accounts. If the sender fails to have insufficient funds in their account to process the transaction, the transaction fails and the tinybars will not be transferred to the receiving account. The service fee will still be charged in the case of insufficient funds.

{% hint style="info" %}
There are `100_000_000` tinybars in one hbar. 
{% endhint %}

| Constructor | Description |
| :--- | :--- |
| `CryptoTransferTransaction()` | Initializes the CryptoTransferTransaction object |

```java
new CryptoTransferTransaction()
.addSender()
.addRecipient()
.setMaxTransactionFee()
.setNodeAccountId()
.setTransactionId()
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
      <td style="text-align:left"><code>addSender(&lt;accountId&gt;, &lt;amount&gt;)</code>
      </td>
      <td style="text-align:left">AccountId, long</td>
      <td style="text-align:left">The sender is the account ID of the account and the amount (value) of
        tinybars that will be withdrawn from that account. The amount being withdrawn
        from the sender has to equal the amount that will be deposited into the
        recipient account. This method can be called multple times.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>addRecipient(&lt;accountId&gt;, &lt;amount&gt;)</code>
      </td>
      <td style="text-align:left">AccountId, long</td>
      <td style="text-align:left">The recipient is account ID of the account the tinybars will be deposited
        into and the amount (value). The amount being withdrawn from the sender
        account has to equal the amount that will be deposited into the recipient
        account.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMaxTransactionFee(&lt;fee&gt;)</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">The maximum fee to be paid for this transaction executed by this client.
        The actual fee may be less, but will never be greater than this value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setNodeAccountId(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountId</td>
      <td style="text-align:left"><b>TBD</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTransactionId(&lt;transactionId&gt;)</code>
      </td>
      <td style="text-align:left">TransactionId</td>
      <td style="text-align:left"><b>TBD</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMemo(&lt;memo&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>A short note attached to the transaction</p>
        <p>Max: 100 bytes</p>
      </td>
    </tr>
  </tbody>
</table>## Example

```java
// Transfer X hbar from the operator of the client to the given account ID
Transaction transaction = new CryptoTransferTransaction()
     .addSender(OPERATOR_ID, 10000)
     .addRecipient(AccountId.fromString("0.0.3"), 10000)
     .build(client);

transaction.execute(client);
// queryReceipt() waits for consensus
transaction.getReceipt(client);

System.out.println("transferred 10_000 tinybar...");
```

