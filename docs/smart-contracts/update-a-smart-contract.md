---
description: ContractUpdateTransaction
---

# Update a smart contract

`ContractUpdateTransaction()` updates an existing smart contract instance to the given parameter values. Any null field is left unchanged.

| Constructor | Description |
| :--- | :--- |
| `ContractUpdateTransaction()` | Initializes the ContractUpdateTransaction object |

```java
new ContractUpdateTransaction()
     .setContractId()
     .setFileId()
     .setAdminKey()
     .setAutoRenewPeriod()
     .setExpirationTime()
     .setProxyAccount()
     .setMaxTransactionFee()
     .setMemo()
     .build()
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setContractId(&lt;contractId&gt;)</code>
      </td>
      <td style="text-align:left"><a href="../user-defined-data-types.md#contractid">ContractId</a>
      </td>
      <td style="text-align:left">The contract ID instance to update</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setFileId(&lt;fileId&gt;)</code>
      </td>
      <td style="text-align:left"><a href="../user-defined-data-types.md#fileid">FileId</a>
      </td>
      <td style="text-align:left">The file ID of file containing the smart contract bytecode</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAdminKey(&lt;key&gt;)</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java">Ed25519PublicKey</a>
      </td>
      <td style="text-align:left">The state of the instance can be modified arbitrarily if this key signs
        a transaction to modify it. If this is null, then such modifications are
        not possible, and there is no administrator that can override the normal
        operation of this smart contract instance.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewPeriod(&lt;duration&gt;)</code>
      </td>
      <td style="text-align:left">Duration</td>
      <td style="text-align:left">The instance will charge its account every this many seconds to renew
        for this long. Duration type is in seconds. For example, one hour duration
        would result in the value of 3,600 seconds.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setExpirationTime(&lt;expiration&gt;)</code>
      </td>
      <td style="text-align:left">Instant</td>
      <td style="text-align:left">Extend the expiration of the instance and its account to this time.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setProxyAccount(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left"><a href="../user-defined-data-types.md#accountid">AccountId</a>
      </td>
      <td style="text-align:left">ID of the account to which this account is proxy staked.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMaxTransactionFee(&lt;fee&gt;)</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">The maximum fee to be paid for this transaction executed by this client.
        The actual fee may be less, but will never be greater than this value.</td>
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

```

