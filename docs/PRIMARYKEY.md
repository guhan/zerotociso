# Primary Key
A primary key is a column or a set of columns in a relational database table that uniquely identifies each row (record) in that table. It serves as a means of enforcing data integrity and ensuring that each row in the table has a unique identifier. 

## Uniqueness
The primary key must contain unique values for each row in the table. No two rows can have the same primary key value.
## Uniqueness Enforcement
The database management system (DBMS) enforces the uniqueness constraint of the primary key, preventing the insertion of duplicate values into the primary key column(s).
## Data Integrity
A primary key ensures data integrity by guaranteeing the uniqueness of rows. It prevents data anomalies, such as duplicate records, which can lead to incorrect query results and data inconsistency.
## Indexed
Most DBMSs automatically create an index on the primary key column(s). This index speeds up data retrieval for queries that involve the primary key column(s).
## Relationships
Primary keys are often used to establish relationships between tables in a relational database. In another table, a foreign key can reference the primary key of another table to create a relationship or link between the two tables.
## Single or Composite
A primary key can consist of a single column or a combination of columns. When a primary key consists of multiple columns, it is known as a composite primary key.
## Null Values
In most relational database systems, primary key columns cannot contain null values. This ensures that each row has a valid and unique identifier.


## What are best practices in choosing a primary key?
It's important to choose primary keys carefully, as they play a critical role in database design. Common choices for primary keys include auto-incremented integers, unique identifiers (e.g., UUIDs), or natural keys (e.g., social security numbers, email addresses) if they are guaranteed to be unique.
