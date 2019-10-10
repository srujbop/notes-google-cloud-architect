# Cloud Bigtable

[Cloud Bigtable](https://cloud.google.com/bigtable/docs/overview) is a fully managed, high performance NoSQL database service for large analytical and operational workloads.

Fast access to extremly large datasets (>terabytes, petabytes) while updating these datasets continuouesly.

HBase - opensource implementation based on Bigtable paper

Began as the storage system for the __web search index__ at Google

Designed to handle large amounts of replicated, rapidly changing data and can be queried quickly wiht high concurrency (high throughput), while maintaining string consistency throughput.

A sparse, distributed, persistent, multi-dimentional sorted map (can go back in time)

Rebalances data

It supports HBase API for access and native compatibility with Hadoop systems.

## Design goals

* Large amount of (replicated) data 
* Low latency, high throughput (millions of queries per second)
* Rapidly changing data
* History of data changes
* Strong consistency
* Row-level transactions (does not need ttransactional semantics across multiple rows)
* Subset selection


## Features

* Scale to billions of rows and thousands of columns (petabytes of data).
* Each row has a key that is indexed.
* Ideal for storing very large amounts of single-keyed data.
* High read and write throughput at very low latency (great for MapReduce operations).
* Simple administration handling upgrades and restarts transparently.
* Cluster resizing without downtime.
* Sparse storage where empty cells do not take up any space.
* Data is encrypted in-flight and at rest.
* Supports Role based ACLs.
* Data access can be through Application API, Streaming, or Batch Processing.
* Integrates with Cloud Dataflow and Cloud Dataproc.
* On-premise to cloud base operations supported.
* Can use Hadoop to both export and reimport data using Google Cloud Dataproc - a managed Hadoop service

## When to Use

Use Bigtable when you need very high throughput and scalability for non-structured key/value data where each value is typically less than 10 MB.

Bigtable also excels for:

* MapReduce operations.
* Stream processing / analytics.
* Machine learning applications.

* Terabytes or more data
* Usage sustained over a long period of time
* Tens to hundreds of thousands of queries per second
* Basic access to data - lookups and simple scan across keys

## Architecture

Instances, clusters, nodes, tablets (can be combined, split, and moved to other nodes)

## Limitations

* No secondary indexes (no "where")
* No multirow transactional semantics
* Have to think ahead about what type of questions you will want to ask about your data
* Have to choose row-key carefully to maintain performance
* Need to choose schema carelfully
* Costly - minimum $1400 per month (vs $30 minimum for Cloud SQL)

## Pricing

compute + storage + network

## ELI5

What is HBase?

> HBase is an open-source, non-relational, distributed database modeled after Google's Bigtable and is written in Java. It is developed as part of Apache Software Foundation's Apache Hadoop project and runs on top of HDFS (Hadoop Distributed File System), providing Bigtable-like capabilities for Hadoop. That is, it provides a fault-tolerant way of storing large quantities of sparse data.

_Credit [Wikipedia](https://en.wikipedia.org/wiki/Apache_HBase)_
