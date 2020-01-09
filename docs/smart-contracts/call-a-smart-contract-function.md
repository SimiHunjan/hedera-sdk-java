# Call a smart contract function

`ContractCallQuery()` calls a function from a smart contract instance without updating its state or requiring consensus.

| Constructor | Description |
| :--- | :--- |
| `ContractCallQuery()` | Initializes a ContractCallQuery object |

| Method | Type | Description |
| :--- | :--- | :--- |
| `setContractId(<contractId>)` | [ContractId](../user-defined-data-types.md#contractid) | The ID of the contract instance to call |
| `setGas(<gas>)` | long | Gas amount to run the constructor |
| `setFunctionParameters(<parameters>)` | Callparams\(&lt;function&gt;\) | Which funtion to call from the contract instance and the parameters |
| `setMaxResultSize(<size>)` | long | Max number of bytes that the result might include. The run will fail if it would have returned more than this number of bytes. |

## Example

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

FunctionResult contractCallResult = new ContractCallQuery()
    .setGas(30000)
    .setContractId(newContractId)
    .setFunctionParameters(CallParams.function("greet"))
    .execute(client);
```

