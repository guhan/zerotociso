# Databases

## Key Concepts
- **Concurrency**: edit control, ensures to make sure information is always correct. Uses a lock feature to
  ensure only one write at one time. 
- **Polyinstantiation**: two rows have the same primary key but have different data and are classified at different security levels.

## Types
- **Heiarchical**: records and fields are listed in a logical tree structure
- **Distributed**: data is stored in two or more databases that are logically connected and appear
  as a single database
  - Examples: Apache Cassandra, Amazon DynamoDB, Riak.
- **Relational**:flat two dimensional tables of rows and columns where there is a mapping (_relation_)
  between tables
  - **Cardinality**: number of rows
  - **Degree**: number of columns
  - Examples: MySQL, PostgreSQL, Oracle Database, Microsoft SQL Server.
- **NoSQL Databases**:
  - These databases are designed to handle unstructured or semi-structured data and provide more flexibility than RDBMS.
  - NoSQL databases are categorized into several subtypes, including:
    - Document databases (e.g., MongoDB, Couchbase): Store data in JSON-like documents.
    - Key-Value stores (e.g., Redis, DynamoDB): Use a key to retrieve data.
    - Column-family stores (e.g., Apache Cassandra, HBase): Organize data in column families.
    - Graph databases (e.g., Neo4j, Amazon Neptune): Focus on relationships between data entities.
- **Object-Oriented Databases (OODBMS)**:
  - These databases are designed to store complex data structures, including objects and classes.
  - They are closely aligned with object-oriented programming paradigms.
  - Examples: db4o, ObjectDB.
- **In-Memory Databases**:
  - These databases store data in memory (RAM) rather than on disk for extremely fast data access.
  - They are often used for caching and real-time analytics.
  - Examples: Redis, Memcached.
- **Time-Series Databases**:
  - These databases are optimized for storing and querying time-stamped data, such as sensor readings, logs, and metrics.
  - They provide efficient storage and retrieval for time-series data.
  - Examples: InfluxDB, Prometheus, OpenTSDB.
- **Spatial Databases**:
  - Spatial databases are specialized for storing and querying geographic or spatial data, such as maps, GPS coordinates, and shapes.
  - They support spatial indexing and spatial operations.
  - Examples: PostGIS (extension for PostgreSQL), MongoDB Spatial.
- **NewSQL Databases**:
  - NewSQL databases attempt to combine the scalability of NoSQL databases with the ACID properties of traditional relational databases.
  - They are designed for high scalability and performance while maintaining strong data consistency.
  - Examples: Google Spanner, CockroachDB.
- **Graph Databases**:
  - These databases are designed for managing and querying data with complex relationships, making them suitable for social networks, recommendation systems, and network analysis.
  - Examples: Neo4j, Amazon Neptune, ArangoDB.
- **Multimodel Databases**:
  - Multimodel databases allow the storage and retrieval of data in multiple formats and models within the same database system.
  - They offer flexibility in handling different types of data.
  - Examples: ArangoDB, OrientDB.
 
## Candidate Keys
In a database management system (DBMS), a candidate key is a set of one or more attributes (columns) within a relational database table that uniquely identifies each row (tuple) in that table. Candidate keys play a fundamental role in defining the integrity and structure of a relational database. Here are some key points to understand about candidate keys:

- **Uniqueness**: Each candidate key must guarantee that it contains unique values for each row in the table. This means that no two rows in the table can have the same combination of values in the candidate key columns.
- **Irreducibility**: A candidate key is minimal, meaning that no subset of its columns can also uniquely identify rows in the table. In other words, removing any attribute from the candidate key would result in a non-unique identifier.
- **No Duplicate Values**: The values within the candidate key columns should not contain duplicate entries. This ensures that each row is uniquely identifiable.
- **Primary Key**: From the set of candidate keys, one is typically chosen as the primary key. The primary key is the candidate key that is used to establish relationships between tables through foreign keys. It is also used as a reference point for indexing and organizing data efficiently.
- **Alternate Candidate Keys**: If there are multiple candidate keys in a table (which is common), the ones not chosen as the primary key are referred to as alternate candidate keys.

## Primary Keys
In a relational database management system (DBMS), a primary key is a special type of database constraint used to uniquely identify each row (record) in a table. It serves as a means of ensuring data integrity and providing a reference point for establishing relationships between tables. Here are the key characteristics and aspects of a primary key:

- **Uniqueness**: A primary key constraint enforces the uniqueness of values in the designated column(s) or attribute(s) within the table. This means that no two rows in the table can have the same value(s) in the primary key column(s).
- **Uniquely Identifying Rows**: The primary key uniquely identifies each row in the table. This property is crucial for distinguishing one record from another within the same table.
- **No Null Values**: In most database systems, primary key columns cannot contain null values. This ensures that every row in the table has a valid, non-null identifier.
- **Indexed for Efficiency**: Primary key columns are typically automatically indexed by the DBMS. This indexing improves the speed of data retrieval operations, such as searching for specific rows or joining tables.
- **Relationships**: Primary keys are used to establish relationships between tables in a relational database. They serve as the basis for foreign keys in related tables, allowing for referential integrity and the creation of associations between data across multiple tables.
- **Single or Composite**: A primary key can consist of a single column or a combination of multiple columns. In the case of a composite primary key, the combination of values in those columns must be unique.


## Foreign Keys
In a relational database management system (DBMS), a foreign key is a database constraint that establishes a link between two tables by enforcing referential integrity. It defines a relationship between the data in two separate tables, typically between a "parent" table (referenced table) and a "child" table (referring table). The foreign key in the child table references the primary key in the parent table. Here are the key characteristics and aspects of foreign keys:

- **Referential Integrity**: The primary purpose of a foreign key is to maintain referential integrity, which ensures that relationships between data in different tables remain consistent and valid. It prevents the creation of orphaned records in the child table by enforcing that the values in the foreign key column(s) must correspond to values in the primary key column(s) of the parent table.
- **Relationships**: Foreign keys establish relationships between tables. They define how records in the child table are associated with records in the parent table. This allows you to model complex relationships and associations between different sets of data.
- **Child Table**: The table _containing the foreign key is called the child table_ or referring table. It is the table that references the primary key in the parent table.
- **Parent Table**: The table whose primary key is referenced by the foreign key is called the parent table or referenced table. It is the table that contains the unique identifier(s) that the foreign key in the child table refers to.
- **Data Integrity**: Foreign keys help maintain data integrity by preventing actions that would violate referential integrity, such as inserting, updating, or deleting records in a way that would leave references in an inconsistent state.
- **Actions on Update or Delete**: Foreign keys can specify what should happen when a referenced record in the parent table is updated or deleted. Common options include cascading changes (updating or deleting related records in the child table), setting to NULL, or restricting the operation if it would create an inconsistency.




