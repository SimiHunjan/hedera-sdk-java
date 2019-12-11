---
description: Retrieving the address book for the Hedera network
---

# Address Book

The address book contains the node ID and and node address information required to sync with Hedera node\(s\).  The address book file ID is `0.0.102`. You can obtain the address book information by requesting the contents of the file `0.0.12` \([`FileContentsQuery()`](file-service-1/get-file-contents.md)\).

### Example:

```java
// To improve responsiveness, you should specify multiple nodes using the
// `Client(<Map<AccountId, String>>)` constructor instead
Client client = new Client(NODE_ID, NODE_ADDRESS);

// Defaults the operator account ID and key such that all generated transactions will be paid for
// by this account and be signed by this key
client.setOperator(OPERATOR_ID, OPERATOR_KEY);

final FileContentsQuery fileQuery = new FileContentsQuery()
    .setFileId(FileId.ADDRESS_BOOK);

final long cost = fileQuery.getCost(client);
System.out.println("file contents cost: " + cost);

fileQuery.setMaxQueryPayment(100000000);

final ByteString contents = fileQuery.execute(client).getFileContents().getContents();

Files.copy(contents.newInput(),
    FileSystems.getDefault().getPath("address-book.proto.bin"));
```

