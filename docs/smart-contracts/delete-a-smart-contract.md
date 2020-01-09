# Delete a smart contract

| Constructor | Description |
| :--- | :--- |
| `ContractDeleteTransaction()` | ​Initializes the ContractDeleteTransaction object |

| Method | Type | Description |
| :--- | :--- | :--- |
| `setContractId(<contractID>)` | ContractID | The ID of the contract |

## Example <a id="example"></a>

```java
// create the contract's bytecode file
TransactionId fileTxId = new FileCreateTransaction().setExpirationTime(
    Instant.now()
        .plus(Duration.ofSeconds(3600)))
    // Use the same key as the operator to "own" this file
    .addKey(OPERATOR_KEY.getPublicKey())
    .setContents(byteCodeHex.getBytes())
    .execute(client);

TransactionReceipt fileReceipt = fileTxId.getReceipt(client);
FileId newFileId = fileReceipt.getFileId();

System.out.println("contract bytecode file: " + newFileId);

// create the contract itself
TransactionId contractTxId = new ContractCreateTransaction()
    .setAutoRenewPeriod(Duration.ofHours(1))
    .setGas(217000)
    .setBytecodeFile(newFileId)
    // set an admin key so we can delete the contract later
    .setAdminKey(OPERATOR_KEY.getPublicKey())
    .execute(client);

TransactionReceipt contractReceipt = contractTxId.getReceipt(client);

System.out.println(contractReceipt.toProto());

ContractId newContractId = contractReceipt.getContractId();

System.out.println("new contract ID: " + newContractId);

// now delete the contract
TransactionId contractDeleteTxnId = new ContractDeleteTransaction()
    .setContractId(newContractId)
    .execute(client);

TransactionReceipt contractDeleteResult = contractDeleteTxnId.getReceipt(client);

if (contractDeleteResult.getStatus() != ResponseCodeEnum.SUCCESS) {
    System.out.println("error deleting contract: " + contractDeleteResult.getStatus());
    return;
}
System.out.println("Contract successfully deleted");

```

