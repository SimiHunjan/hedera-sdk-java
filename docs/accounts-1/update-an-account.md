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

## Example

```java
xxxx 
```

