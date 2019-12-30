---
description: Standard HAPI data types derived from the HAPI definition
---

# Specialized Data Types

## [AccountId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/account/AccountId.java)

An `AccountId` is composed of a &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;accountNum&gt; \(eg. 0.0.10\).

* **shardNum** represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard.
* **realmnNum** represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* **accountNum** represents the account number \(`accountId`\)

Together these values make up your `AccountId`. When an `AccountId` is requested, be sure all three values are included.

| Constructor | Type | Description |
| :--- | :---: | :--- |
| `AccountId(<shardNum>,<realmNum>,<accountNum>)` | long, long, long | Constructs an `AccountId` with 0 for `shardNum` and `realmNum` \(e.g., `0.0.<accountNum>`\) |

```java
new AccountId(); 
```

| Method | Type | Description |
| :--- | :--- | :--- |
| `AccountId.fromString(<account>)` | string | Constructs an `AccountId` from a string formatted as &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;accountNum&gt; |
| `AccountId.fromSolidityAddress(<address>)` | string | Constructs an `AccountId` from a solidity address in string format  |

### Example

```java
AccountId accountId = new AccountId(0 ,0 ,10);
System.out.println(accountId);

// Construct accountId from String
AccountId accountId = AccountId.fromString("0.0.10");
System.out.println(accountId);

```

## [FileId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/file/FileId.java)

A `FileId` is composed of a &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;fileNum&gt; \(eg. 0.0.15\).

* **shardNum** represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard.
* **realmnNum** represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* **fileNum** represents the file number

Together these values make up your accountId. When an `FileId` is requested, be sure all three values are included.

```java
new FileId();
```

| Constructor | Type | Description |
| :--- | :---: | :--- |
| `FileId(<shardNum>,<realmNum>,<fileNum>)` | long, long, long | Constructs an `FileId` with 0 for `shardNum` and `realmNum` \(e.g., `0.0.<fileNum>`\) |

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
      <td style="text-align:left"><code>FileId.fromString()</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>Constructs an <code>FileId</code> from a string formatted as</p>
        <p>&lt;shardNum&gt;.&lt;realmNum&gt;.&lt;fileNum&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>FileId.fromSolidityAddress()</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Constructs an <code>FileId</code> from a solidity address in string format</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>FileId.ADDRESS_BOOK</code>
      </td>
      <td style="text-align:left">FileId</td>
      <td style="text-align:left">The public node address book for the current network</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>FileId.EXCHANGE_RATES</code>
      </td>
      <td style="text-align:left">FileId</td>
      <td style="text-align:left">The current exchange rate of HBAR to USD</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>FileId.FEE_SCHEDULE</code>
      </td>
      <td style="text-align:left">FileId</td>
      <td style="text-align:left">The current fee schedule for the network</td>
    </tr>
  </tbody>
</table>### Example

```java
FileId fileId = new FileId(0,0,15);
System.out.println(fileId);

//Contruct FileId from string
FileId fileId = FileId.fromString("0.0.15");
System.out.println(fileId);
```

## [ContractId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/contract/ContractId.java)

A `ContractId` is composed of a &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;contractNum&gt; \(eg. 0.0.20\).

* **shardNum** represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard.
* **realmnNum** represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* **contractNum** represents the contract number

```java
new ContractId(); 
```

Together these values make up your `ContractId`. When an `ContractId` is requested, be sure all three values are included.

| Constructor | Type | Description |
| :--- | :--- | :--- |
| `ContractId(<shardNum>,<realmNum>,<contractNum>)` | long, long, long | Constructs a `ContractId` with 0 for `shardNum` and `realmNum` \(e.g., `0.0.<contractNum>`\) |

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
      <td style="text-align:left"><code>ContractId.fromString(&lt;account&gt;)</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>Constructs a <code>ContractId </code>from a string formatted as</p>
        <p>&lt;shardNum&gt;.&lt;realmNum&gt;.&lt;contractNum&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ContractId.fromSolidityAddress(&lt;address&gt;)</code>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Constructs a <code>ContractId</code> from a solidity address in string format</td>
    </tr>
  </tbody>
</table>### Example

```java
ContractId contractId = new ContractId(0,0,20);
System.out.println(contractId);

// Construct ContractId from string
ContractId contractId = ContractId.fromString("0.0.20");
System.out.println(contractId);
```

