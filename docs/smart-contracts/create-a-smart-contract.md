---
description: ContractCreateTransaction
---

# Create a smart contract

`ContractCreateTransaction()` creates a new smart contract instance. The ID of the smart contract can be obtained from the record or receipt. The instance will run the bytecode stored in the given file, referenced either by FileID or by the transaction ID of the transaction that created the file. The constructor will be executed using the given amount of gas. Similar to accounts, the instance will exist for autoRenewSeconds and when it is reached the instance will renew itself for another autoRenewSeconds seconds. The associated cryptocurrency account will be charged for each auto-renew period.

{% hint style="warning" %}
**Smart Contract State Size**

Each smart contract has a maximum state size of 1MB which can store up to approximately 16,000 key-value pairs.
{% endhint %}

## Constructor

| Constructor | Description |
| :--- | :--- |
| `ContractCreateTransaction()` | Initializes the ContractCreateTransaction\(\) |

## Methods

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setAdminKey(<key>)` | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) | The state of the instance and its fields can be modified arbitrarily if this key signs a transaction to modify it. If this is null, then such modifications are not possible, and there is no administrator that can override the normal operation of this smart contract instance. |
| `setByteCodeFile(<fileId>)` | FileId | The `fileId` of the file that contains the smart contract bytecode |
| `setGas(<gas>)` | long | Gas amount to run the constructor |
| `setInitialBalance(<amount>)` | long | The initial number of tinybars to put into the cryptocurrency account associated with and owned by the smart contract. |
| `setAutoRenewPeriod(<duration>)` | Duration | The period of time in which the smart contract will auto-renew in seconds. Duration type is in seconds. For example, one hour would result in the input value of 3600 seconds. |
| `setMaxTransactionFee(<fee>)` | long | The maximum fee to be paid for this transaction executed by this client. The actual fee may be less, but will never be greater than this value. |
| `setMemo(<memo>)` | String | Any notes or descriptions that should be put into the record \(max length 100\) |

## Example

```java
// create the contract's bytecode file
TransactionId fileTxId = new FileCreateTransaction().setExpirationTime(
    Instant.now()
        .plus(Duration.ofSeconds(3600)))
    // Use the same key as the operator to "own" this file
    .addKey(OPERATOR_KEY.getPublicKey())
    .setContents(byteCodeHex.getBytes())
    .execute(client);

TransactionReceipt fileReceipt = fileTxId.getReceipt(client);
FileId newFileId = fileReceipt.getFileId();

System.out.println("contract bytecode file: " + newFileId);

// create the contract itself
TransactionId contractTxId = new ContractCreateTransaction()
    .setAutoRenewPeriod(Duration.ofHours(1))
    .setGas(217000)
    .setBytecodeFile(newFileId)
    // set an admin key so we can delete the contract later
    .setAdminKey(OPERATOR_KEY.getPublicKey())
    .execute(client);

TransactionReceipt contractReceipt = contractTxId.getReceipt(client);

System.out.println(contractReceipt.toProto());

ContractId newContractId = contractReceipt.getContractId();

System.out.println("new contract ID: " + newContractId);
```

