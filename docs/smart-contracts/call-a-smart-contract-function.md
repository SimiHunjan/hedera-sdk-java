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
| `setMaxQueryPayment(<maxPayment>)` | long |  |
| `setPaymentAmount(<transaction>)` | Transaction |  |

## Example

```java

```

