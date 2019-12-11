# User-defined Data Types

## [AccountId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/account/AccountId.java)

| Method | Description |
| :--- | :--- |
| **`AccountId.fromString()`** | Constructs an `AccountId` from a string formatted as &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;accountNum&gt; |
| **`AccountId.fromSolidityAddress()`** | Constructs an `AccountId` from a solidity address in string format  |

## [FileId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/file/FileId.java)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b><code>FileId.fromString() </code></b>
      </td>
      <td style="text-align:left">
        <p>Constructs an <code>FileId</code> from a string formatted as</p>
        <p>&lt;shardNum&gt;.&lt;realmNum&gt;.&lt;fileNum&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b><code>FileId.fromSolidityAddress()</code></b>
      </td>
      <td style="text-align:left">Constructs an <code>FileId</code> from a solidity address in string format</td>
    </tr>
    <tr>
      <td style="text-align:left"><b><code>FileId.ADDRESS_BOOK</code></b>
      </td>
      <td style="text-align:left">The public node address book for the current network</td>
    </tr>
    <tr>
      <td style="text-align:left"><b><code>FileId.EXCHANGE_RATES</code></b>
      </td>
      <td style="text-align:left">The current exchange rate of HBAR to USD</td>
    </tr>
    <tr>
      <td style="text-align:left"><b><code>FileId.FEE_SCHEDULE</code></b>
      </td>
      <td style="text-align:left">The current fee schedule for the network</td>
    </tr>
  </tbody>
</table>## [ContractId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/contract/ContractId.java)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b><code>ContractId.fromString()</code></b>
      </td>
      <td style="text-align:left">
        <p>Constructs an <code>FileId</code> from a string formatted as</p>
        <p>&lt;shardNum&gt;.&lt;realmNum&gt;.&lt;contractNum&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b><code>ContractId.fromSolidityAddress()</code></b>
      </td>
      <td style="text-align:left">Constructs an <code>ContractId</code> from a solidity address in string
        format</td>
    </tr>
  </tbody>
</table>