# Update a topic

Updates the properties of an existing topic

| Constructor | Description |
| :--- | :--- |
| `ConsensusTopicUpdateTransaction()` | Initializes the ConsensusTopicUpdateTransaction object |

```java
new ConsensusTopicUpdateTransaction()
```

## Basic

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setTopicId(<topicId>)` | TopicID | The ID of the topic to update |
| `setAdminKey(<key>)` | ED25519PublicKey | Access control for update/delete of the topic. If unspecified, no change. If empty keyList - the adminKey is cleared. |
| `setSubmitKey(<key>)` | ED25519PublicKey | Access control for ConsensusService.submitMessage.  If unspecified, no change. If empty keyList - the submitKey is cleared. |

### Example

```java

```

## Advanced

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setTopicMemo(<memo>)` | String | Short publicly visible memo about the topic. No guarantee of uniqueness. Null for "do not update". |
| `setExpirationTime(<expirationTime>)` | Instant | Effective consensus timestamp at \(and after\) which all consensus transactions and queries will fail. The expirationTime may be no longer than MAX\_AUTORENEW\_PERIOD \(8000001 seconds\) from the consensus timestamp of this transaction. On topics with no adminKey, extending the expirationTime is the only updateTopic option allowed on the topic. If unspecified, no change. |
| `setAutoRenewPeriod(<duration>)` | Duration | The amount of time to extend the topic's lifetime automatically at expirationTime if the autoRenewAccount is configured and has funds \(once autoRenew functionality is supported by HAPI\). If unspecified, no change. |
| `setAutoRenewAccountId(<autoRenewAccountId>)` | AccountId | Optional account to be used at the topic's expirationTime to extend the life of the topic. Once autoRenew functionality is supported by HAPI, the topic lifetime will be extended up to a maximum of the autoRenewPeriod or however long the topic can be extended using all funds on the account \(whichever is the smaller duration/amount\). If specified as the default value \(0.0.0\), the autoRenewAccount will be removed. If unspecified, no change. |
| `setTransactionValidDuration(<duration>)` | Duration |  |
| `setNodeAccountId(<accountId>)` | AccountId |  |
| `setMemo(<memo>)` | String |  |
| `sign(<key>)` |  |  |

### Example

```java

```

