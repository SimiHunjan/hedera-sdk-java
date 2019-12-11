---
description: Establishing a connection to a Hedera network
---

# Client

When building the client you will need the following pieces of information:

* Node ID & Node Address
  * The node ID is the ID of the node in the format of &lt;shardNum&gt;.&lt;realmNum&gt;.&lt;
  * Num&gt;
* Operator ID & Operator key

```java
new Client()
.setOperator()
.setMaxTransacactionFee()

```

