---
description: Standard HAPI data types derived from the HAPI definition
---

# Specialized Types

## [AccountId](https://github.com/hashgraph/hedera-sdk-java/blob/v0.8.0/src/main/java/com/hedera/hashgraph/sdk/account/AccountId.java)

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
      <td style="text-align:left"><code>AccountId.fromString(&lt;account&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Constructs an <code>AccountId</code> from a string formatted as &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;accountNum&gt;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>AccountId.fromSolidityAddress(&lt;address&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Constructs an <code>AccountId</code> from a solidity address in string format</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getRealmNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>Returns the realm number from the <code>AccountId</code>
        </p>
        <p>default: 0</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getAccountNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">Returns t<code>he accountNum</code> from the <code>AccountId</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getShardNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">Returns the <code>shardNum</code> from the <code>AccountId</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>toProto()</code>
      </td>
      <td style="text-align:left">AccountID</td>
      <td style="text-align:left">Returns the protobuf</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>toString()</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Returns the AccoutId in string format</td>
    </tr>
  </tbody>
</table>### Example

```java
AccountId accountId = new AccountId(0 ,0 ,10);
System.out.println(accountId);

// Construct accountId from String
AccountId accountId = AccountId.fromString("0.0.10");
System.out.println(accountId);

```

## [FileId](https://github.com/hashgraph/hedera-sdk-java/blob/v0.8.0/src/main/java/com/hedera/hashgraph/sdk/file/FileId.java)

A `FileId` is composed of a &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;fileNum&gt; \(eg. 0.0.15\).

* **shardNum** represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard.
* **realmnNum** represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* **fileNum** represents the file number

Together these values make up your accountId. When an `FileId` is requested, be sure all three values are included.

| Constructor | Type | Description |
| :--- | :---: | :--- |
| `FileId(<shardNum>,<realmNum>,<fileNum>)` | long, long, long | Constructs an `FileId` with 0 for `shardNum` and `realmNum` \(e.g., `0.0.<fileNum>`\) |

```java
new FileId();
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
      <td style="text-align:left"><code>FileId.fromString()</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>Constructs an <code>FileId</code> from a string formatted as</p>
        <p>&lt;shardNum&gt;.&lt;realmNum&gt;.&lt;fileNum&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>FileId.fromSolidityAddress()</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Constructs an <code>FileId</code> from a solidity address in string format</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getRealmNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>Returns the realm number from the <code>FileId</code>
        </p>
        <p>default: 0</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getFileNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">Returns the <code>fileNum</code> from the <code>FileId</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getShardNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>Returns the <code>shardNum</code> from the <code>FileId</code>
        </p>
        <p>default: 0</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>toProto()</code>
      </td>
      <td style="text-align:left">FileID</td>
      <td style="text-align:left">Returns the protobuf message</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>toString()</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Returns the FileId in string format</td>
    </tr>
  </tbody>
</table>### Example

```java
FileId fileId = new FileId(0,0,15);
System.out.println(fileId);

//Construct FileId from string
FileId fileId = FileId.fromString("0.0.15");
System.out.println(fileId);
```

## [ContractId](https://github.com/hashgraph/hedera-sdk-java/blob/v0.8.0/src/main/java/com/hedera/hashgraph/sdk/contract/ContractId.java)

A `ContractId` is composed of a &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;contractNum&gt; \(eg. 0.0.20\).

* **shardNum** represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard.
* **realmnNum** represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* **contractNum** represents the contract number

Together these values make up your `ContractId`. When an `ContractId` is requested, be sure all three values are included.

| Constructor | Type | Description |
| :--- | :--- | :--- |
| `ContractId(<shardNum>,<realmNum>,<contractNum>)` | long, long, long | Constructs a `ContractId` with 0 for `shardNum` and `realmNum` \(e.g., `0.0.<contractNum>`\) |

```java
new ContractId(); 
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
      <td style="text-align:left"><code>ContractId.fromString(&lt;account&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>Constructs a <code>ContractId </code>from a string formatted as</p>
        <p>&lt;shardNum&gt;.&lt;realmNum&gt;.&lt;contractNum&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ContractId.fromSolidityAddress(&lt;address&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Constructs a <code>ContractId</code> from a solidity address in string format</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getRealmNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>Returns the realm number from the <code>ContractId</code>
        </p>
        <p>default: 0</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getContractNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">Returns the <code>contractNum</code> from the <code>ContractId</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getShardNum()</code>
      </td>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>Returns the <code>shardNum</code> from the <code>ContractId</code>
        </p>
        <p>default: 0</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>toProto()</code>
      </td>
      <td style="text-align:left">ContractID</td>
      <td style="text-align:left">Returns the protobuf message</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>toString()</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Returns the ContractId in string format</td>
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

## [TransactionId](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/TransactionId.java)

A `TransactionId` is composed of the valid start time and the account ID that is signing the transaction. Every transaction has an assciated `TransactionId`. The `TransactionId` should never be set by a user unless in very special circumstances.

| Constructor | Type | Description |
| :--- | :--- | :--- |
| `TransactionId(<accountId>)` | AccountId | Generates a new transaction ID for the given `accountId`. |

```java
new TransactionId()
```

| Methods | Type | Description |
| :--- | :--- | :--- |
| `getAccountId()` | AccountId | Returns the AccountId |
| `getValidStart()` | Instant | Returns the valid start time |
| `toProto()` | TransactionID | Returns the protobuf message |

### Example

```java
TransactionId transactionId = new TransactionId(accountId);
System.out.println(transactionId.toProto());

```

