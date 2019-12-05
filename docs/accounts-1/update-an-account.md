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



<table>
  <thead>
    <tr>
      <th style="text-align:left">Property</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>setAccountForUpdate(</b> &lt;accountId&gt; <b>)</b>
      </td>
      <td style="text-align:left">
        <p>The ID of the account to update in this transaction</p>
        <p></p>
      </td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>setAutoRenewPeriod( </b>&lt;duration&gt;<b> )</b>
      </td>
      <td style="text-align:left">The period of time in which the account will auto-renew in seconds. Duration
        type is in seconds. For example, one hour would result in the input value
        of <code>3600 </code>seconds</td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>setExpirationTime( </b>&lt;timestamp&gt; <b>)</b>
      </td>
      <td style="text-align:left">The new expiration time to extend to.</td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>setKey(</b> &lt;key&gt; <b>)</b>
      </td>
      <td style="text-align:left">The public key generated for the new account.</td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>setSendRecordThreshold( </b>&lt;long&gt;<b> )</b>
      </td>
      <td style="text-align:left">Creates a record for any transaction that withdraws more than x value
        of tinybars.</td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>setReceiveRecordThreshold( </b>&lt;long&gt; <b>)</b>
      </td>
      <td style="text-align:left">Creates a record for any transaction that deposits more than x value of
        tinybars.</td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>setProxyAccount( </b>&lt;accountId&gt; <b>)</b>
      </td>
      <td style="text-align:left">ID of account to which this account should be proxy staked.</td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>setTransactionFee(</b> &lt;long&gt;<b> )</b>
      </td>
      <td style="text-align:left">The transaction fee (node fee, service fee, and network fee combined)
        to process the transaction.</td>
      <td style="text-align:left">None</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>sign(</b> &lt;key&gt; <b>)</b>
      </td>
      <td style="text-align:left">The private key of the account executing and paying for the transaction.
        The transaction does not need to be explicitiy signed if the signer is
        the operator.</td>
      <td style="text-align:left">None</td>
    </tr>
  </tbody>
</table>