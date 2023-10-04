# Foreign Key
A foreign key is a column or a set of columns in a relational database table that establishes a link or relationship between two tables. It defines a constraint that enforces referential integrity, ensuring that the values in the foreign key column(s) of one table match the values in the primary key column(s) of another table. Foreign keys are used to maintain data consistency and to create relationships between related tables in a relational database.

## Relationships
Foreign keys are used to define relationships between tables in a relational database. These relationships are typically one of the following types

- One-to-Many (1
N)
A common type of relationship where one row in one table can be associated with multiple rows in another table. For example, a "Customer" table may have a one-to-many relationship with an "Orders" table, where each customer can have multiple orders.
-  Many-to-One (N
1)
The reverse of a one-to-many relationship, where multiple rows in one table can be associated with a single row in another table. For example, multiple orders in an "Orders" table may be associated with a single customer in a "Customers" table.
-  Many-to-Many (N
N)
A more complex relationship where multiple rows in one table can be associated with multiple rows in another table. This type of relationship is typically implemented using an intermediary table, often referred to as a junction table or bridge table.
## Referential Integrity
Foreign keys enforce referential integrity by ensuring that the values in the foreign key column(s) correspond to valid values in the primary key column(s) of the referenced table. This prevents the creation of "orphaned" records that have no valid parent record in the referenced table.
## Data Integrity
Foreign keys help maintain data integrity by preventing the insertion or update of data that would violate the defined relationships. For example, if a foreign key constraint exists between an "Orders" table and a "Customers" table, attempting to insert an order for a non-existent customer would result in an error.
## Indexed
In most database management systems (DBMSs), foreign key columns are often automatically indexed for performance optimization, especially in scenarios where joins between tables are common.
## Cascading Actions
Foreign key constraints can define cascading actions that specify what should happen when a referenced record in the parent (referenced) table is modified or deleted. Common cascading actions include cascading updates and cascading deletes.
