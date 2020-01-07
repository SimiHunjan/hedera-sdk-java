# Mirror Node Client

Constructs the mirror node client.

| Constructor | Type | Description |
| :--- | :--- | :--- |
| `ConsensusClient(<endpoint>)` | String | Initializes the ConsensusClient object |

```java
new ConsensusClient();
```



### Example

```java
private static final String MIRROR_NODE_ADDRESS = Objects.requireNonNull(Dotenv.load().get("MIRROR_NODE_ADDRESS"));

final ConsensusClient consensusClient = new ConsensusClient(MIRROR_NODE_ADDRESS);
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
      <td style="text-align:left"><code>subscribe(&lt;topicId, listener)</code>
      </td>
      <td style="text-align:left">ConsensusTopicId, Consumer&lt;ConsensusMessage&gt;</td>
      <td style="text-align:left">
        <p></p>
        <p>Subscribe to a Consensus Service topic; the callback will receive messages
          with consensus timestamps starting now and continuing indefinitely into
          the future.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>subscribe(&lt;topicId, consensusStartTime, listener)</code>
      </td>
      <td style="text-align:left">ConsensusTopicId, Instant, Consumer&lt;ConsensusMessage&gt;</td>
      <td style="text-align:left">
        <p></p>
        <p>Subscribe to a Consensus Service topic; the callback will receive messages</p>
        <p>with consensus timestamps falling on or after the given {@link Instant}</p>
        <p>(which may be in the past or future) and continuing indefinitely afterwards.</p>
        <p></p>
        <p><code>consensusStartTime</code>: the lower bound for timestamps (inclusive),
          may be in the past or future.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getMessasges(&lt;topic, startTime, endTime)</code>
      </td>
      <td style="text-align:left">TopicId, Instant, Instant</td>
      <td style="text-align:left">
        <p></p>
        <p>Get a blocking iterator which returns messages for the given topic with
          consensus timestamps</p>
        <p>between two Instants.</p>
        <p></p>
        <p><code>startTime</code>: the lower bound for timestamps (inclusive), may
          be in the past or future.</p>
        <p><code>endTime</code> : the upper bound for timestamps (exclusive), may
          also be in the past or future.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getMessageUntil(&lt;topic, endTime&gt;)</code>
      </td>
      <td style="text-align:left">TopicId, Instant</td>
      <td style="text-align:left">
        <p></p>
        <p>Get a blocking iterator which returns messages for the given topic with
          consensus timestamps starting now and continuing until the given Instant</p>
        <p><code>endTime</code> : the upper bound for timestamps (exclusive), may
          be in the past or future.</p>
      </td>
    </tr>
  </tbody>
</table>### Example

```java

```

