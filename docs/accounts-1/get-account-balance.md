# Get account balance

`AccountBalanceQuery()` returns the account balance. The account is charged tinybars each time the request is executed.

```java
client.getAccountBalance(OPERATOR_ID)
```

```java
new AccountBalanceQuery()
.setAccountId()
.build();
```

## Example

```java
// see `.env.sample` in the repository root for how to specify these values // or set environment variables with the same names
private static final AccountId NODE_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("NODE_ID")));
private static final String NODE_ADDRESS = Objects.requireNonNull(Dotenv.load().get("NODE_ADDRESS"));
private static final AccountId OPERATOR_ID = AccountId.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_ID")));
private static final Ed25519PrivateKey OPERATOR_KEY = Ed25519PrivateKey.fromString(Objects.requireNonNull(Dotenv.load().get("OPERATOR_KEY")));

private GetAccountBalance() { }

public static void main(String[] args) throws HederaException {
    // To improve responsiveness, you should specify multiple nodes using the
    // `Client(<Map<AccountId, String>>)` constructor instead
    Client client = new Client(NODE_ID, NODE_ADDRESS);

    // Defaults the operator account ID and key such that all generated transactions will be paid for
    // by this account and be signed by this key
    client.setOperator(OPERATOR_ID, OPERATOR_KEY);

    long balance = client.getAccountBalance(OPERATOR_ID);

    System.out.println("balance = " + balance);
}
```



