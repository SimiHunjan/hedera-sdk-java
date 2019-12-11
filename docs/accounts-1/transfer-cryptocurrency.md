# Transfer cryptocurrency

`CryptoTransferTransaction()` transfers tinybars from one Hedera account to different Hedera account on the Hedera network. The amount is in **tinybars** \(not hbars\). The transaction must be signed by all the keys from all sender accounts. If the sender fails to have insufficient funds in their account to process the transaction, the transaction fails and the tinybars will not be transferred to the receiving account. The service fee will still be charged in the case of insufficient funds.

{% hint style="info" %}
There are `100_000_000` tinybars in one hbar.
{% endhint %}

## Basic

```text
client.transferCryptoTo(<accountID>,<long>);
```

## Advanced

```java
new CryptoTransferTransaction()
.addSender(accountID, amount)
.addRecipient(accountId, amount)
.build(client);
```

## Crypto Transfer Example

```java
public final class TransferCrypto {

    // see `.env.sample` in the repository root for how to specify these values // or set environment variables with the same names
    private static final AccountId NODE_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("NODE_ID")));
    private static final String NODE_ADDRESS = Objects.requireNonNull(Dotenv.load().get("NODE_ADDRESS"));
    private static final AccountId OPERATOR_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_ID")));
    private static final Ed25519PrivateKey OPERATOR_KEY = Ed25519PrivateKey.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_KEY")));

    private TransferCrypto() { }

    public static void main(String[] args) throws HederaException {
        // To improve responsiveness, you should specify multiple nodes using the
        // `Client(<Map<AccountId, String>>)` constructor instead
        Client client = new Client(NODE_ID, NODE_ADDRESS);

        // Defaults the operator account ID and key such that all generated transactions will be paid for
        // by this account and be signed by this key
        client.setOperator(OPERATOR_ID, OPERATOR_KEY);

        // Transfer X hbar from the operator of the client to the given account ID
        Transaction transaction = new CryptoTransferTransaction()
            .addSender(OPERATOR_ID, 10000)
            .addRecipient(AccountId.fromString("0.0.3"), 10000)
            .build(client);

        transaction.execute(client);
        // queryReceipt() waits for consensus
        transaction.getReceipt(client);

        System.out.println("transferred 10_000 tinybar...");
    }
```

