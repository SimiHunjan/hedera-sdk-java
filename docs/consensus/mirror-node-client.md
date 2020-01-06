# Mirror Node Client

| Constructor |  | Description |
| :--- | :--- | :--- |
| `ConsensusClient(<endpoint>)` | String | Intializes the ConsensusClient object |

```java
new ConsensusClient()
```

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
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getMessasges()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>