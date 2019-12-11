# User-defined Data Types

## [AccountId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/account/AccountId.java)

An `accountId` is composed of a &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;accountNum&gt; \(eg. 0.0.10\).

* **shardNum** represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard.
* **realmnNum** represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* **accountNum** represents the account number \( `accountId` \)

Together these values make up your accountId. When an `accountId` is requested, be sure all three values are included.

| Method | Description |
| :--- | :--- |
| **`AccountId.fromString()`** | Constructs an `AccountId` from a string formatted as &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;accountNum&gt; |
| **`AccountId.fromSolidityAddress()`** | Constructs an `AccountId` from a solidity address in string format  |

```java
AccountId accountId = AccountId.fromString("0.0.10");
System.out.println(accountId);
```

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
</table>```java
FileId fileId = FileId.fromString("0.0.10");
System.out.println(fileId);
```

## [ContractId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/contract/ContractId.java)

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
</table>```java
ContractId contractId = ContractId.fromString("0.0.10");
System.out.println(contractId);
```

