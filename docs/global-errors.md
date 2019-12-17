# Global Errors

| Error  | Description |
| :--- | :--- |
| `BUSY` | If API is throttled out |
| `OK` | The transaction passed the precheck validations. |
| `INVALID_TRANSACTION` | For any error not handled by specific error codes listed below. |
| `PAYER_ACCOUNT_NOT_FOUND` | Payer account does not exist. |
| `INVALID_NODE_ACCOUNT` | Node Account provided does not match the node account of the node the transaction was submitted to. |
| `TRANSACTION_EXPIRED` | Pre-Check error when TransactionValidStart + transactionValidDuration is less than current consensus time. |
| `INVALID_TRANSACTION_START` | Transaction start time is greater than current consensus time |
| `INVALID_TRANSACTION_DURATION` | valid transaction duration is a positive non zero number that does not exceed 120 seconds |
| `INVALID_SIGNATURE` | The transaction signature is not valid |
| `MEMO_TOO_LONG` | Transaction memo size exceeded 100 bytes |
| `INSUFFICIENT_TX_FEE` | The fee provided in the transaction is insufficient for this type of transaction |
| `INSUFFICIENT_PAYER_BALANCE` | The payer account has insufficient cryptocurrency to pay the transaction fee |
| `DUPLICATE_TRANSACTION` | This transaction ID is a duplicate of one that was submitted to this node or reached consensus in the last 180 seconds \(receipt period\) |
| `NOT_SUPPORTED` | The API is not currently supported |

