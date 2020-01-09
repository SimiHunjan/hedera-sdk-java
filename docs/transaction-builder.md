# Transactions

The following methods can be called when building the following transaction types:

| Cryyptocurrency Accounts | File Service | Smart Contracts |
| :--- | :--- | :--- |
| AccountCreateTransaction | FileCreateTransaction | ContractCreateTransaction |
| AccountUpdateTransaction | FileAppendTransaction | ContractUpdateTransaction |
| CryptoTransferTransaction | FileUpdateTransaction | ContractDeleteTransaction |
| AccountDeleteTransaction | FileDeleteTransaction |  |



| Methods | Type | Description |
| :--- | :--- | :--- |
| `setTransactionId(<transactionId>)` | TransactionId | Sets the ID for this transaction, which includes the payer's account \(the account paying the transaction fee\). If two transactions have the same transactionID, they won't both have an effect. |
| `setNodeId(<accountId>)` | AccountId | Sets the account of the node that submits the transaction to the network. |
| `setMaxTransactionFee(<fee>)` | long | Sets the maximum fee, in tinybar, that the client is willing to pay to execute this transaction, which is split between the network and the node. The actual fee assessed may be less than this, in which case you will only be charged that amount. An error is thrown if the assessed fee is greater than this. |
| `setTransactionValidDuration(<duration>)` | Duration | Sets the the duration that this transaction is valid for. The transaction must reach consensus before this elapses. The duration will be capped at 2 minutes as that is the maximum for the network.  |
| `setTransactionMemo(<memo>)` | String | Sets any notes or description that should be put into the transaction record \(if one is requested\). Note that a max of length of 100 is enforced. |
| `sign(<key>)` |  | Expliclity sign the transaction with a private key |
| `execute(<client>)` | Client | Submits the transaction to the Hedera network for consensus  |
| `build()` |  | Builds the transaction |



