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
| `setTopicId(<topicId>)` | TopicID | The ID of the topic to update |
| `setTopicMemo(<memo>)` | String | Short publicly visible memo about the topic. No guarantee of uniqueness. Null for "do not update". |
| `setAdminKey(<key>)` | ED25519PublicKey | Access control for update/delete of the topic. If unspecified, no change. If empty keyList - the adminKey is cleared. |
| `setSubmitKey(<key>)` | ED25519PublicKey | Access control for ConsensusService.submitMessage.  If unspecified, no change. If empty keyList - the submitKey is cleared. |
| `setExpirationTime(<expirationTime>)` | Instant | Effective consensus timestamp at \(and after\) which all consensus transactions and queries will fail. The expirationTime may be no longer than MAX\_AUTORENEW\_PERIOD \(8000001 seconds\) from the consensus timestamp of this transaction. On topics with no adminKey, extending the expirationTime is the only updateTopic option allowed on the topic. If unspecified, no change. |
| `setAutoRenewPeriod(<duration>)` | Duration |  |
| `setAutoRenewAccountId(<autoRenewAccountId>)` | AccountId |  |
| `setMaxTransactionFee(<fee>)` | long |  |
| `setTransactionId(<transactionId>)` | TransactionId |  |
| `setTransactionValidDuration(<duration>)` | Duration |  |
| `setNodeAccountId(<accountId>)` | AccountId |  |

## 

## Example

```java

```

