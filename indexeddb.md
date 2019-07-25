![Logo](./img/UPWT.png)
# BC.IndexedDB
Included in every modern browser is a database called IndexedDB. IndexedDB is a noSQL or document database which is a standard maintained by the World Wide Web Consortium (W3C). IndexedDB is the standard browser database in use currently and is used by many applications and solutions.

## How the platform uses IndexedDB
IndexedDB is used as the database for the unblocked platform. It is where both application configuration and your data is stored. Data you store in the IndexedDB database is automatically distributed among other users on the platform using the following process.

1. You define the data operation
2. This operation is converted to C# code
3. The data within the C# Code is encrypted leveraging the recipient's public key
4. The C# is compiled and signed with your private key
5. The C# is sent to the unblocked node.
6. The node sends to all other nodes who verify the data (without seeing the data itself)
7. A **founder** node eventually writes this to a block in the distributed ledger
8. If a node finds a private key that will decrypt the C# data, it decrypts and runs the C#
9. The data is updated in the recipients IndexedDB
10. The recipients UI updates to show the change

The process above occurs automatically, without manual intervention.