# Summary

* __CloudSQL__ - __relational__, transactional, OLTP. MySQL & PostgreSQL. Not low-latency retrieval of time-series data.

* __Bigtable__ - Petabyte-scale. Optimized for __time-series data__. highly available, __low-latency__. Managed service.

* __Datastore__ - Horizontally scalable document DB

* __BigQuery__ - serverless, highly-scalable, and cost-effective cloud __data warehouse and analytics__ with an in-memory BI Engine and __machine learning__ built in. Higher latency than Bigtable. There is quota.

* __DataProc__ - optimized to create ephemeral job-scoped clusters in around 90 seconds. This speed of deployment means that a single job can have a dedicated cluster, containing just the resources needed to run the job, that is shut down upon job completion.

* __Cloud Memorystore__ - Managed Redis

* __Cloud Spanner__ - Horizontally scalable relational DB

* __Cloud Storage__ - Cheapest per-byte storage offered by google 

* __Cloud Filestore__ is a managed (serverless) file storage service for applications that require a filesystem interface and a shared filesystem for data. Filestore gives users a simple, native experience for standing up managed __Network Attached Storage (NAS)__ with their Google Compute Engine and Kubernetes Engine instances. The ability to fine-tune Filestore’s performance and capacity independently leads to predictably fast performance for your file-based workloads.


# Google Cloud Storage

There are a number of different storage options in the Google Cloud Platform.

[![Choosing a Storage Option](/Storage/storage-options.svg)](https://cloud.google.com/products/storage/)


## Comparing Storage Options

|                 | Cloud Storage  | Cloud Datastore | Cloud Bigtable          | Cloud SQL   | Cloud Spanner |
|-----------------|----------------|-----------------|-------------------------|-------------|---------------|
| Storage Type    | BLOB           | NoSQL Document  | NoSQL Wide / HBase API  | SQL         | Global SQL    |
| Capacity        | PB+            | TB+             | PB+                     | 500GB       | 2TB per node  |
| Unit Size       | 5TB per Object | 1MB per Entity  | Cell: ~10MB Row: ~100MB | SQL Limits  | 10MB per col  |
| Read            | Copy to Disk   | Filter on Prop  | Scan Rows               | SELECT Rows | SELECT Rows   |
| Write           | One File       | Put Object      | Put Row                 | INSERT Row  | INSERT Row    |
| Granularity     | Object         | Attribute       | Row                     | Field       | Field         |
| Transaction     | No             | Yes             | No                      | Yes         | Yes           |
| Complex Queries | No             | No              | No                      | Yes         | Yes           |
| Good For        | Bin or Object  | App Engine      | Flat Heavey Read/Write  | Web / Apps  | Scalable Apps |

## Type of storage systems

* Memorstore - a managed Redis service
  * Cache
  * 1GB - 300GB 
  * Configure failover replicas for high availability
  * Specify region & zone
* Persistent storage - durable block storage attached VMs
  * Support __file system__
  * Not directly attached to VMs but network accessible
  * HDDs & SSDs
  * Automatically encrypted 
  * Zonal & regional
* Object storage - Cloud storage
  * Does not support concurrency and locking
  * No file system
  * __Buckets__
  * Storage class:
    * Multiregional & Reginal 
    * Nearline & coldline (access charges)
    * Can change storage class of an object using lifecycle management
    * Multiregional and regional storage objects can be changed to nearline or coldline
    * Nearline can only be changed to coldline
  * Live version
  
## Storage Data Models

* Object storage - Cloud storage. Treats file as atomic objects
* Relational - Cloud SQL, Cloud Spanner, BigQuery
  * Cloud SQL (machine type) - web applications, business intellignece, e-commerce applications
  * Spanner (nodes) - global supply chains, financial services applications
  * BigQuery (dataset) - works with large numbers of rows and columns of data. NOT sutible for transaciton-oriented applications
* NoSQL - Datastore, Cloud Firestore, Bigtable
  * Cloud Datastore
    * document database
    * entity  
    * for nonanalytic, nonrelational storage needs
    * no schema, no relational operations
    * kind 
  * Cloud Firestore - managed NoSQL database that uses document data model
    * Designed for storing, synchronizing, and querying data across distributed applications, like __mobile__ application
    * Apps can be automatically updated in close to real time when data is changed on the backend
    * Supports transactions
    * Provides multiregional replication
    * Native mode vs Datastore mode
  * Bigtable - wide-column database
    * Designed for petbyte-scale database
    * IoT data, analytic processing, data science applications, timeseries
    * Low-millisecond latency
    * Scales horizontally
    * Designed for high volume and high-velocity of ingest

## Choosing a storage solution

* Read & write patterns
* Consistency
* Transaction support
* Cost
* Latency
