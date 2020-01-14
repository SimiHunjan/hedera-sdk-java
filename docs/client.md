---
description: Establishing a connection to a Hedera network
---

# Client

You will need the following pieces of information to construct your Hedera client. 

**User Information**

The operator is the user paying for the transactions fees.  

* **Operator ID:** The account ID of the user paying for the transaction/query fees
* **Operator key:** The private key of the user paying for the transaction/query fees

**Network Information**

You can find testnet and mainnet network details by logging into your Hedera portal. 

* **Node ID:** The account ID of the node submitting the transaction to the network
* **Node Address:** The network address of the node submitting the transaction to the network

You can store these variables in a .env file at the root directory of the sdk. Please see the [env.sample](https://github.com/hashgraph/hedera-sdk-java/blob/master/.env.sample) file in the SDK for how to set this up.

## Basic

The ExampleHelper class helps you build a client easily. The helper class grabs the envrionment configuration variables from the .env file. 

```java
Client client = ExampleHelper.createHederaClient();
```

| Methods | Type | Description |
| :--- | :--- | :--- |
| `createHederaClient()` | Client | Build the Hedera client. Obtains the envrionment configuration from the .env file in the root directory |
| `getOperatorKey()` | ED25519PrivateKey | Returns the private key of the operator  |
| `getOperatorId()` | AccountId | Returns the AccountId of the operator  |
| `getNodeId()` | AccountId | Returns the nodeId of the client |

## Advanced

<table>
  <thead>
    <tr>
      <th style="text-align:left">Constructor</th>
      <th style="text-align:center">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>Client(&lt;nodeAccountId&gt;, &lt;nodeURL&gt;)</code>
      </td>
      <td style="text-align:center">AccountId, String</td>
      <td style="text-align:left">
        <p>Constructs a client object</p>
        <p>Map&lt;AccountId, String&gt;</p>
      </td>
    </tr>
  </tbody>
</table>```java

```

<table>
  <thead>
    <tr>
      <th style="text-align:left">Methods</th>
      <th style="text-align:center">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>setMaxTransactionFee(&lt;maxTransactionFee&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">Set the maximum fee to be paid for transactions executed by this client.
        The actual fee may be less, but will never be greater than this value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setMaxQueryPayment(&lt;maxQueryPayment&gt;)</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">Set the maximum default payment value allowable for queries.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setOperator(&lt;operatorId&gt;, &lt;operatorKey&gt;)</code>
      </td>
      <td style="text-align:center">
        <p>AccountId,</p>
        <p>ED25519PrivateKey</p>
      </td>
      <td style="text-align:left">Defaults the operator account ID and key such that all generated transactions
        will be paid for by this account Id and and signed by this key</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>TransferCryptoTo(&lt;recipient&gt;, amount)</code>
      </td>
      <td style="text-align:center">AccountId, long</td>
      <td style="text-align:left">Transfers the amount tinybars to the recipient</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>createAccount(&lt;publicKey , initialBalance&gt;)</code>
      </td>
      <td style="text-align:center">PublicKey, long</td>
      <td style="text-align:left">Creates a new account</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>putNode(&lt;nodeAccountId&gt;, &lt;nodeURL&gt;)</code>
      </td>
      <td style="text-align:center">AccountId, String</td>
      <td style="text-align:left">Insert or update a node in the client</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getAccount()</code>
      </td>
      <td style="text-align:center">AccountId</td>
      <td style="text-align:left">Returns the account</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getAccountBalance(&lt;accountId&gt;)</code>
      </td>
      <td style="text-align:center">AccountId</td>
      <td style="text-align:left">Returns the account balance</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getMaxQueryPayment()</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">Returns the maximum payment value</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>getMaxTransactionFee()</code>
      </td>
      <td style="text-align:center">long</td>
      <td style="text-align:left">Returns the set maximum fee</td>
    </tr>
  </tbody>
</table>{% hint style="warning" %}
The **max transaction fee** and **max query payment** are both set to 1\_000\_000 tinybar \(1 hbar\).  This amount can be modified by editing the [Client.java](https://github.com/hashgraph/hedera-sdk-java/blob/master/src/main/java/com/hedera/hashgraph/sdk/Client.java) class or by using `setMaxTransactionFee()` and `setMaxQueryPayment()`when building the transaction or query.
{% endhint %}

### Create Client Example

 **.env file:**

{% tabs %}
{% tab title="Single Node" %}
```text
# Network Node ID and Address
NODE_ID= <node account ID>
NODE_ADDRESS= x.testnet.hedera.com:PORT_NUMBER

# Operator ID and Private Key
OPERATOR_ID= //accountId of the account paying for tranasactions
OPERATOR_KEY= //ED25519 Private Key associated with the account
```
{% endtab %}

{% tab title="Multiple Nodes" %}
```java
# Network Node ID and Address
NODE_ID_1= node AccountId
NODE_ADDRESS_1= x.testnet.hedera.com:PORT_NUMBER
NODE_ID_2= node AccountId
NODE_ADDRESS_2= x.testnet.hedera.com:PORT_NUMBER
NODE_ID_3= node AccountId
NODE_ADDRESS_3= x.testnet.hedera.com:PORT_NUMBER

# Operator ID and Private Key
OPERATOR_ID= AccountId
OPERATOR_KEY= <ED25519 Private Key>
```
{% endtab %}
{% endtabs %}

**Java file:**

{% tabs %}
{% tab title="Single Node" %}
```java
Client client = new Client(NODE_ID, NODE_ADDRESS);
// Defaults the operator account ID and key such that all generated transactions will be paid for
// by this account and be signed by this key
client.setOperator(OPERATOR_ID, OPERATOR_KEY);
```
{% endtab %}

{% tab title="Multiple Nodes" %}
```java
Client client = new Client(Map.of(NODE_ID_1, NODE_ADDRESS_1, NODE_ID_2, NODE_ADDRESS_2, NODE_ID_3, NODE_ADDRESS_3));
// Defaults the operator account ID and key such that all generated transactions will be paid for
// by this account and be signed by this key
client.setOperator(OPERATOR_ID, OPERATOR_KEY);
```
{% endtab %}
{% endtabs %}

