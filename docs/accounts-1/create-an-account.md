---
description: AccountCreateTransaction()
---

# Create an account

The account represents your account specific to the Hedera network. Accounts are required to utilize the Hedera network services and to pay network transaction fees. Hedera account IDs have the format: x.y.z. eg 0.0.3. where:

* x represents the shard number \(`shardId`\). It will default to 0 today, as Hedera only performs in one shard
* y represents the realm number \(`realmId`\). It will default to 0 today, as realms are not yet supported.
* z represents the account number \( `accountId` \)

Together these values make up your accountId. When an `accountId` is requested, be sure all three values are included.

{% hint style="info" %}
When creating a new account an existing account will need to fund the initial balance and pay for the transaction fee.
{% endhint %}

## Basic

The easiest way to create an account is using `.createAccount()`. with the simple client. `createAccount()` requires two properties, the public key to be associated with the new account and the initial balance in tinybars.

```java
client.setMaxTransactionFee().createAccount(PublicKey, initialBalance);
```

## Advanced

Additional properties can be set when creating a new account object. The properties and their descriptions can be found below.

```java
new AccountCreateTransaction()
  .setKey()
  .setInitialBalance()
  .setAutoRenewPeriod()
  .setReceiverSignatureRequired()
  .setReceiveRecordThreshold()
  .setSendRecordThreshold();
```

### Descriptions

| Property | Type | Description | Default Value |
| :--- | :--- | :--- | :--- |
| `setKey()` | key | The private key generated for the new account. | None |
| `setInitialBalance()` | uint64 | The initial balance for the account in tinybars | None |
| `setTransactionFee()` | duration | The transaction fee for the account create transaction | None |
| `setAutoRenewPeriod()` | long | The period of time in which the account will auto-renew in seconds. The account is charged tinybars for every auto-renew period. Duration type is in seconds. For example, one hour would result in the input value of 3,600 seconds.NOTE: This is fixed to approximately 3 months \(7890000 seconds\). Any other value will return the following error: AUTORENEW\_DURATION\_NOT\_IN\_RANGE. | 2,592,000 seconds |
| `setReceiverSignatureRequired()` | boolean |  | False |

## Example:

```java
public final class CreateAccount {

    // see `.env.sample` in the repository root for how to specify these values
    // or set environment variables with the same names
    private static final AccountId NODE_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("NODE_ID")));
    private static final String NODE_ADDRESS = Objects.requireNonNull(Dotenv.load().get("NODE_ADDRESS"));
    private static final AccountId OPERATOR_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_ID")));
    private static final Ed25519PrivateKey OPERATOR_KEY = Ed25519PrivateKey.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_KEY")));

    private CreateAccount() { }

    public static void main(String[] args) throws HederaException {
        // Generate a Ed25519 private, public key pair
        Ed25519PrivateKey newKey = Ed25519PrivateKey.generate();
        Ed25519PublicKey newPublicKey = newKey.getPublicKey();

        System.out.println("private key = " + newKey);
        System.out.println("public key = " + newPublicKey);

        // To improve responsiveness, you should specify multiple nodes using the
        // `Client(<Map<AccountId, String>>)` constructor instead
        Client client = new Client(NODE_ID, NODE_ADDRESS);

        // Defaults the operator account ID and key such that all generated transactions will be paid for
        // by this account and be signed by this key
        client.setOperator(OPERATOR_ID, OPERATOR_KEY);

        Transaction tx = new AccountCreateTransaction()
            // The only _required_ property here is `key`
            .setKey(newKey.getPublicKey())
            .setInitialBalance(1000)
            .setMaxTransactionFee(10000000)
            .build(client);

        tx.execute(client);

        // This will wait for the receipt to become available
        TransactionReceipt receipt = tx.getReceipt(client);

        AccountId newAccountId = receipt.getAccountId();

        System.out.println("account = " + newAccountId);
    }
}
```

