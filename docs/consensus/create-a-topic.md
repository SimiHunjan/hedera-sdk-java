# Create a topic

Creates a new topic.

| Constructor | Description |
| :--- | :--- |
| `ConsensusTopicCreateTransaction()` | Initializes the ConsensusTopicCreateTransaction object |

```java
new ConsensusTopicCreateTransaction()
```

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setMaxTransactionFee(<fee>)` | long | The maximum fee to be paid for this transaction executed by this client. The actual fee may be less, but will never be greater than this value. |
| `setAdminKey(<key>)` | ED25519PublicKey | The key that has the ability to update or delete the topic. expirationTime can be modified by anyone. If no adminKey is specified, updateTopic may only be used to extend the expirationTime, and deletTopic is disallowed. |
| `setSubmitKey(<key>)` | ED25519PublicKey | Access control for submitMessage. If this property is not set, no access control is performed on ConsensusService.submitMessage \(all submissions aloud\).  |
| `setAutoRenewPeriod(<autoRenewPeriod>)` | Duration | The initial lifetime of the topic and the amount of time to attempt to extend the topic's lifetime by |
| `setTopicMemo(<memo>)` | String | Short publicly visible memo about the topic. No guarantee of uniqueness. |
| `build()` |  |  |
| `execute(<client>)` | Client |  |

## Example

```java
 final TransactionId transactionId = new ConsensusTopicCreateTransaction()
     .setMaxTransactionFee(1_000_000_000)
     .execute(client);
```

