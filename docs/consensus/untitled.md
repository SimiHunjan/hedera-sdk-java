# Update a topic

Updates the properties of an existing topic

| Constructor | Description |
| :--- | :--- |
| `ConsensusTopicUpdateTransaction()` | Initializes the ConsensusTopicUpdateTransaction object |

```java
new ConsensusTopicUpdateTransaction()
```

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setTopicId(<topicId>)` | TopicID |  |
| `setTopicMemo(<memo>)` | String |  |
| `setAdminKey(<key>)` | ED25519PublicKey |  |
| `setSubmitKey(<key>)` | ED25519PublicKey |  |
| `setExpirationTime(<expirationTime>)` | Instant |  |
| `setAutoRenewPeriod(<duration>)` | Duration |  |
| `setAutoRenewAccountId(<autoRenewAccountId>)` | AccountId |  |
| `setMaxTransactionFee(<fee>)` | long |  |
| `setTransactionId(<transactionId>)` | TransactionId |  |
| `setTransactionValidDuration(<duration>)` | Duration |  |
| `setNodeAccountId(<accountId>)` | AccountId |  |

## Example

```java

```

