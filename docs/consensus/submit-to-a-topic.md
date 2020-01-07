# Submit to a topic

Submit a message to a topic.

| Constructor | Description |
| :--- | :--- |
| `ConsensusMessageSubmitTransaction()` | Initializes a ConsensusMessageSubmitTransaction object |

```java
new ConsensusMessageSubmitTransaction()
```

## Basic

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setTopicID(<topic>` | TopicID | The ID of the topic to submit a message to |
| `setMessage(<message>)` | byte\[ \] | The message to submit in byte format. Max size of the Transaction \(including signatures\) is 4kB. |
| `setMessage(<message>)` | String | The message to submit in string format |

### Example

```java

```

## Advanced

| Methods | Types | Description |
| :--- | :--- | :--- |
| `setMaxTransactionFee(<fee>)` | long |  |
| `setTransactionId(<transactionId>)` | TransactionId |  |
| `setTransactionValidDuration(<duration>)` | Duration |  |
| `setNodeAccountId(<accountId>)` | AccountId |  |
| `setMemo(<memo>)` | String |  |
| `sign(<key>)` |  |  |

### Example

```java

```

