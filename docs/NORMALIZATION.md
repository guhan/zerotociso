# Normalization
Database normalization is a process in the field of relational database design that helps reduce data redundancy and improve data integrity by organizing data into separate tables and ensuring that data dependencies are properly represented. The goal of normalization is to structure the database in a way that minimizes data anomalies (such as insertion, update, and deletion anomalies) and allows for efficient data retrieval while maintaining data consistency. There are several normal forms, each with its own set of rules and requirements, and they are typically represented as Normal Form (NF) levels.



## First Normal Form (1NF)
  - Eliminates repeating groups by ensuring that each column in a table contains only atomic (indivisible) values.
  - Each cell in the table must contain a single value, and there should be no arrays, lists, or nested structures.
## Second Normal Form (2NF)
  - Builds on 1NF and eliminates partial dependencies.
  - A table is in 2NF if it is in 1NF and if non-key attributes (columns) are fully functionally dependent on the entire primary key (composite key).
## Third Normal Form (3NF)
  - Builds on 2NF and eliminates transitive dependencies.
  - A table is in 3NF if it is in 2NF and if non-key attributes are not transitively dependent on the primary key. In other words, non-key attributes should depend only on the primary key and not on other non-key attributes.
## Boyce-Codd Normal Form (BCNF)
  - A more stringent version of 3NF.
  - A table is in BCNF if, for every non-trivial functional dependency (where the dependent attribute is not a superkey), the determinant (the set of attributes on the left side of the dependency) is a superkey.
## Fourth Normal Form (4NF)
  - Addresses multi-valued dependencies.
  - A table is in 4NF if it is in BCNF and has no multi-valued dependencies.
## Fifth Normal Form (5NF)
  - Addresses cases where multiple join dependencies exist.
  - A table is in 5NF if it is in 4NF and it does not have any non-trivial join dependencies.
