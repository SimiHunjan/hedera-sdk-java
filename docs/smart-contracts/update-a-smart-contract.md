---
description: ContractUpdateTransaction
---

# Update a smart contract

`ContractUpdateTransaction()` updates an existing smart contract instance to the given parameter values. Any null field is left unchanged.

| Constructor | Description |
| :--- | :--- |
| `ContractUpdateTransaction()` | Initializes the ContractUpdateTransaction object |

| Method | Type | Description |
| :--- | :--- | :--- |
| `setContractId(<contractId>)` | [ContractId](../user-defined-data-types.md#contractid) | The contract ID instance to update |
| `setFileId(<fileId>)` | [FileId](../user-defined-data-types.md#fileid) | The file ID of file containing the smart contract bytecode |
| `setAdminKey(<key>)` | [Ed25519PublicKey](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/crypto/ed25519/Ed25519PublicKey.java) | The state of the instance can be modified arbitrarily if this key signs a transaction to modify it. If this is null, then such modifications are not possible, and there is no administrator that can override the normal operation of this smart contract instance. |
| `setAutoRenewPeriod(<duration>)` | Duration | The instance will charge its account every this many seconds to renew for this long. Duration type is in seconds. For example, one hour duration would result in the value of 3,600 seconds. |
| `setExpirationTime(<expiration>)` | Instant | Extend the expiration of the instance and its account to this time. |
| `setProxyAccount(<accountId>)` | [AccountId](../user-defined-data-types.md#accountid) | ID of the account to which this account is proxy staked. |

## Example

```java

```

