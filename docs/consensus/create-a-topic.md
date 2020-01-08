# Create a topic

Creates a new topic.

| Constructor | Description |
| :--- | :--- |
| `ConsensusTopicCreateTransaction()` | Initializes the ConsensusTopicCreateTransaction object |

```java
new ConsensusTopicCreateTransaction()
```

## Basic

| Methods | Type | Description |
| :--- | :--- | :--- |
| `setAdminKey(<key>)` | ED25519PublicKey | The key that has the ability to update or delete the topic. expirationTime can be modified by anyone. If no adminKey is specified, updateTopic may only be used to extend the expirationTime, and deleteTopic is disallowed. |

### Example

```java
 final TransactionId transactionId = new ConsensusTopicCreateTransaction()
     .setMaxTransactionFee(1_000_000_000)
     .execute(client);
```

## Advanced

<table>
  <thead>
    <tr>
      <th style="text-align:left">Methods</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Descriptopm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setSubmitKey(&lt;key&gt;)</code>
      </td>
      <td style="text-align:left">ED25519PublicKey</td>
      <td style="text-align:left">Access control for submitMessage. If this property is not set, no access
        control is performed on ConsensusService.submitMessage (all submissions
        aloud).</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewPeriod(&lt;autoRenewPeriod&gt;)</code>
      </td>
      <td style="text-align:left">Duration</td>
      <td style="text-align:left">
        <p>The initial lifetime of the topic and the amount of time to attempt to
          extend the topic&apos;s lifetime by</p>
        <p><em>Not currently supported</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setTopicMemo(&lt;memo&gt;)</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Short publicly visible memo about the topic. No guarantee of uniqueness.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setAutoRenewAccountId(&lt;autoRenewAccountId&gt;)</code>
      </td>
      <td style="text-align:left">AccountId</td>
      <td style="text-align:left">
        <p>Optional account to be used at the topic&apos;s expirationTime to extend
          the life of the topic</p>
        <p><em>Not currently supported</em>
        </p>
      </td>
    </tr>
  </tbody>
</table>