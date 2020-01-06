---
description: Retrieving the address book for the Hedera network
---

# Address Book

The address book contains the node ID and and node address information required to sync with Hedera node\(s\) in a specific network.  The **mainnet** address book file ID is `0.0.102`. You can obtain the address book information by requesting the contents of the file `0.0.102` \([`FileContentsQuery()`](file-service-1/get-file-contents.md)\). The network information can also be found in your Hedera portal account.

The **testnet** address book information is available in the Hedera portal. 

### Example:

```java
final FileContentsQuery fileQuery = new FileContentsQuery()
    .setFileId(FileId.ADDRESS_BOOK);

final long cost = fileQuery.getCost(client);
System.out.println("file contents cost: " + cost);

fileQuery.setMaxQueryPayment(100000000);

final ByteString contents = fileQuery.execute(client).getFileContents().getContents();

Files.copy(contents.newInput(),
    FileSystems.getDefault().getPath("address-book.proto.bin"));
```

### Output File:





