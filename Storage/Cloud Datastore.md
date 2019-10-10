# Cloud Datastore

Highly scalable NoSQL database (key-value document store like Redis, DynamoDB, MongoDB or Memcached) supporting billions of rows. 

Think of __Gmail__

Distributed, highly scalable, replicated

__Eventual consistency__ (data and indexes are updated asynchronously) globally

__Strong consistency__ with data locality. Queries inside a single entity group are strongly consistent.

Data are duplicated for easy access

History: Megastore --> App Engine Store --> Cloud Datastore

## Design Goals

* __Data locality (entity group)__ - Put many pieces of data near each other. 
  * eg. a specific person's email are stored together, and you do not need search across multiple email accounts. 

* __Result-set query scale__ - time of query is propotional only to the number of matching documents (not the total size of the datastore)

* __Automatic replication__ 


## Features

* Automatic scaling and fully managed.
* Built-in redundancy.
* Supports ACID transactions - never need to worry about mutiple updates conflict
* Includes a free daily quota.
* RESTful Interface.
* Simulate on your local machine.

## Terms

* __Kind__: Roughly equivalent to a table in a relational database. Used to categorize entitise for queries.
* __Entity__: A data object with one or more named properties with values. They have an unique id.
  * Primitives
  * Lists
  * Keys
  * Embedded entities
* __Key__: Unique id for an Entity. 
  * Contains both the type of data and teh data's unique ID, eg. Employee:1
  * Keys can be hierarchical, eg. Employee:1:Employee:2
* __Entity Group__: Used to organize highly related data to achieve strong consistency and to enforce transactionality.
  * If two keys have the same parent, they are in the same entity group
* __Operations__: get, put, delete
* __Indexes__: Datastore uses index to make queries possible
  * An index is a specially ordered and maintained dataset to make querying fast
  * Datastore automatically creates an index for each property 
  * Have to create index if need to match multiple properties together (composite index). Eg. find all emails from Steve where Eric is cc'd

## Consistency & replication

* __Eventual consistency__ (data and indexes are updated asynchronously) globally
* __Strong consistency__ with data locality. Queries inside a single entity group are strongly consistent.
* A single entity group can only handle in the range of 10 requests per second

## Backup & restore

* Snapshot is more like a long-exposure photograph of your data, becasue fo the eventual consistency, hard to get an overall state of the data at a single time point
* Disable writes before snapshoting

## Pricing

* Amount of data
* Number of operations

## Limitations

* No relation
* No referencial integrity
* Certain queries need indexes to be possible 

# When to use

* Durability - never loss data
* Througput - extremly large amount of data with large amount of concurrent queries
* Scale - Gmail scale
* Highly available
* Speed is the similar to relational databases, but does not go down as the size of the datastore increases




