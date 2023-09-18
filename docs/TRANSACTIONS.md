# Transactions
A database transaction is a logical unit of work that consists of one or more database operations, typically including one or more SQL statements, which are executed as a single, indivisible, and coherent unit. Transactions are a fundamental concept in database management systems (DBMS) and are designed to ensure the integrity, consistency, and reliability of data within a database. They adhere to the principles of the ACID properties:

## Atomicity
Transactions are atomic, which means they are treated as an all-or-nothing operation. Either all the changes made by the transaction are successfully applied to the database, or none of them are. If any part of the transaction fails, the entire transaction is rolled back, and the database returns to its previous state.
## Consistency
Transactions bring the database from one consistent state to another consistent state. The database must satisfy certain integrity constraints before and after the transaction. If a transaction violates any integrity constraints, it is rolled back.
## Isolation
Transactions are isolated from each other until they are complete. This means that the changes made by one transaction are not visible to other transactions until the first transaction is committed. Isolation levels can be configured to control the degree of isolation between transactions.
## Durability
Once a transaction is successfully committed, its changes are permanent and will survive any subsequent system failures (e.g., power outage or crash). The data changes are stored in a durable form, typically on disk.
