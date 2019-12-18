# Get file info

`FileInfoQuery()` returns all the information related to the file. If a file has expired, there will be no information to retrieve.

| Constructor | Description |
| :--- | :--- |
| `FileInfoQuery()` | Initializes the FileInfoQuery object |

```java
new FileInfoQuery()
    .setFileId()
    .execute();
```

| Method | Type | Description |
| :--- | :--- | :--- |
| `setFileId(<fileId>)` | FileId | The `fileId` of the file to return information for |

## Example

```java
new FileInfoQuery()
    .setFileId()
    .execute();
```

