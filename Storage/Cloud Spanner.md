# Google Cloud Spanner

[Google Cloud Spanner](https://cloud.google.com/spanner/docs/overview) is a fully managed, mission-critical, relational database service that offers transactional consistency at global scale, schemas, SQL (ANSI 2011 with extensions), and automatic, synchronous replication for high availability.

NewSQL, looks and acts like __SQL__, but have the __scaling__ properties of NoSQL.

Rich query, transactional semantics, strong consistency, horizontal scalability. 

Achieve all these by throwing more resources to it. Very EXPENSIVE (minimum about $2000 per month)!

## Features

* Strong consistency.
* Supports ACID transactions
* SQL support with `ALTER` statements for schema changes.
* Managed instances with high availability through transparent, synchronous, built-in data replication.
* Regional and multi-regional instance configurations.
* Integration with IAM including permissions: admin, databaseAdmin, databaseReader, databaseUser, and viewer.
* Can split and redistribute data across more machines
* Instances --> Nodes --> Databases --> Tables
* Does NOT support INSERT, DELETE commands, but can do it with API
* Achieve scale by __sharding__
* Related data is put together for performance. Use __interleaving__ tables to tell Spanner which data should live near and move with other data. Eg. Spanner can interleaving the Employee table and the associated Paycheck table together to keep Employee and their Paycheck data together. 
* Split points are the positions at which data in a table might be split into separate chunks
* You should choose keys that are evently distributed and choose keys that are counting or incrementing

## When to Use

* Relational, structured and semi-structured data.
* High availability.
* Strong consistency.
* Transactional reads and writes.

## When not to use?

* Do not need strongly consistent and horizontally scaling relational database.
* Need an open-source database.

