# Create a topic

Creates a new topic.

| Constructor | Description |
| :--- | :--- |
| `ConsensusTopicCreateTransaction()` |  |

```java
new ConsensusTopicCreateTransaction()
```

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setMaxTransactionFee(<fee>)` | long |  |
| `setAdminKey(<key>)` | ED25519PublicKey |  |
| `setSubmitKey(<key>)` | ED25519PublicKey |  |
| `setAutoRenewPeriod(<autoRenewPeriod>)` | Duration |  |
| `setTopicMemo(<memo>)` | String |  |
| `build()` |  |  |
| `execute(<client>)` | Client |  |

## Example

```java
 final TransactionId transactionId = new ConsensusTopicCreateTransaction()
     .setMaxTransactionFee(1_000_000_000)
     .execute(client);
```

