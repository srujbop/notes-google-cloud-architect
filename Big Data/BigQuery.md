# Google Cloud Platform BigQuery

[BigQuery](https://cloud.google.com/bigquery/what-is-bigquery) is Google's fully managed, petabyte scale, low cost analytics data warehouse. BigQuery is NoOps—there is no infrastructure to manage and you don't need a database administrator—so you can focus on analyzing data to find meaningful insights, use familiar SQL, and take advantage of the pay-as-you-go model.

Scale computing capacity by enormous cluster of machines to execute a SQL query.

Scale storage throughput by sharding

## Features

* Fully-managed analytics data warehouse.
* Near real-time interactive analysis of massive datasets (hundreds of TBs).
* SQL like syntax.
* Zero administration for performance and scale.
* Pay for storage and processing only.
* Discounts for long term data storage.
* Does not have transactions or uniqueness constraints (not a transactional database)

# Points of Interest

* Datasets:
  * Are a grouping mechanism that holds zero or more tables.
  * Are the lowest unit of access control.
  * Are owned by projects.
* Object names are relative to the project.
* Tables:
  * Are the row-column structures that contain actual data within a dataset.
  * Can not have access control.
  * Have a schema.
  * Have strongly-typed columns of values.
  * Support views.
  * Can be virtual defined by an SQL query.
  * Can be external (federated).
  * Can query Cloud Storage directly.
* Can run queries over Cloud Storage, Cloud Datastore, Cloud Bigtable
* Support streaming data into BigQuery
* Can export dataset

## Pricing

* Storage
* Inserting new data into BigQuery
* Querying your data
