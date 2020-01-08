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

<table>
  <thead>
    <tr>
      <th style="text-align:left">Methods</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setTopicMemo(&lt;memo&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Short publicly visible memo about the topic. No guarantee of uniqueness.
        Null for &quot;do not update&quot;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setExpirationTime(&lt;expirationTime&gt;)</code>
      </td>
      <td style="text-align:left">Instant</td>
      <td style="text-align:left">Effective consensus timestamp at (and after) which all consensus transactions
        and queries will fail. The expirationTime may be no longer than MAX_AUTORENEW_PERIOD
        (8000001 seconds) from the consensus timestamp of this transaction. On
        topics with no adminKey, extending the expirationTime is the only updateTopic
        option allowed on the topic. If unspecified, no change.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewPeriod(&lt;duration&gt;)</code>
      </td>
      <td style="text-align:left">Duration</td>
      <td style="text-align:left">
        <p>The amount of time to extend the topic&apos;s lifetime automatically at
          expirationTime if the autoRenewAccount is configured and has funds (once
          autoRenew functionality is supported by HAPI). If unspecified, no change.</p>
        <p><em>Not currently supported</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewAccountId(&lt;autoRenewAccountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountId</td>
      <td style="text-align:left">
        <p>Optional account to be used at the topic&apos;s expirationTime to extend
          the life of the topic. Once autoRenew functionality is supported by HAPI,
          the topic lifetime will be extended up to a maximum of the autoRenewPeriod
          or however long the topic can be extended using all funds on the account
          (whichever is the smaller duration/amount). If specified as the default
          value (0.0.0), the autoRenewAccount will be removed. If unspecified, no
          change.</p>
        <p><em>Not currently supported</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTransactionValidDuration(&lt;duration&gt;)</code>
      </td>
      <td style="text-align:left">Duration</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setNodeAccountId(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountId</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMemo(&lt;memo&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>sign(&lt;key&gt;)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>### Example

```java

```

