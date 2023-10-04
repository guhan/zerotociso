# Apache Cassandra
Apache Cassandra is an open-source distributed NoSQL database management system that is designed for high availability, fault tolerance, and scalability. It was originally developed by Facebook and later open-sourced as an Apache project, becoming one of the most popular NoSQL databases for handling large amounts of data across distributed clusters of commodity hardware. Cassandra is particularly well-suited for use cases where data must be available and resilient to failures, such as real-time big data analytics and time-series data storage.

## Distributed Architecture
Cassandra is designed as a distributed database from the ground up. It provides automatic data distribution and replication across multiple nodes in a cluster, ensuring high availability and fault tolerance. Data is distributed using a partitioning scheme based on a partition key.
## No Single Point of Failure
Cassandra is designed to operate without a single point of failure. Even if some nodes in the cluster fail, data remains accessible and available.
- Need to be careful about how many replicas of data you have, 1 replica means only one copy. 
## Scalability
Cassandra is highly scalable and can be easily expanded by adding more nodes to the cluster. This makes it suitable for handling large datasets and high-throughput workloads.
## Data Model
Cassandra uses a data model similar to a column-family or wide-column store. Data is organized into tables, and each table can have flexible schemas with columns that can vary from row to row.
## Query Language
Cassandra has its query language called CQL (Cassandra Query Language), which is similar to SQL but adapted for the NoSQL data model. It supports data retrieval, insertion, updates, and deletion.
## Tunable Consistency
Cassandra allows you to configure the level of data consistency for read and write operations, offering a balance between consistency and availability. This is often referred to as tunable consistency.
## Replication and Data Centers
Data replication can be configured to distribute data across multiple data centers and geographic regions, providing disaster recovery capabilities and low-latency access for users in different locations.
## Compaction
Cassandra periodically compacts data files to improve read and write performance. It uses a merge-and-sweep process to optimize data storage and access.
- Compaction occurs during reads, multiple copies of data are merged and then older data is tombstoned (marked for deletion)
## Time-Series Data
Cassandra is well-suited for storing time-series data, such as logs, sensor data, and event data, due to its high write throughput and ability to efficiently handle large volumes of data over time.
## Community and Ecosystem
Cassandra has a large and active open-source community and a rich ecosystem of tools and libraries. It integrates with various data processing frameworks like Apache Spark and Apache Kafka.
