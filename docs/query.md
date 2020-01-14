# Queries

The following methods can be called when building the following query types:

| Cryyptocurrency Accounts | File Service | Smart Contracts |
| :--- | :--- | :--- |
| AccountBalanceQuery | FileContentsQuery | ContractCallQuery |
| AccountInfoQuery | FileInfoQuery | ContractByteCodeQuery |
| AccountRecordQuery |  | ContractInfoQuery |
|  |  | ContractRecordQuery |



| Method | Type | Description |
| :--- | :--- | :--- |
| `setQueryPayment(<paymentAmount>)` | Hbar/long | Sets the explicit query payment amount in hbars |
| `setMaxQueryPayment()` | Hbar/long |  |
| `getCost(<client>)` | Client | Returns the cost of the query |
| `execute(<client>)` | Client |  |

