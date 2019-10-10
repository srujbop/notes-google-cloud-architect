# Cloud SQL

[Cloud SQL](https://cloud.google.com/sql/docs/) is a fully-mannaged Database as a Service (PaaS) based on MySQL or PostgreSQL.

Cloud SQL is a VM that's hosted on Google Compute Engine.

Cloud SQL's focus isn't to be a better, faster MySQL, it's to be a simpler, lower-overhead MySQL.

Cloud SQL makes it easy to setup, maintain, manage and administor your RDBMS in the cloud.

## Features

* MySQL or PostgreSQL databases in the cloud.
* Backups and patches are automatic.
* Replicas are simple.
* Pay-per-use model. Start small and scale up as needed.
* Encrypted in transit and at rest.
* Firewall configuration to grant access.
* Vertically scalable (16 cores, 100GB RAM).
* Horizontal scaling with read-only replicas.
* Access control through native Database security.
* Familiar database with native tools.

## Commands

gcloud sql instnaces list

## Production

* Access control
  * Grant access to CIDR patterns and individual IP addressess
  * SSL
  * Configure maintenance window
  * No access to my.cnf, control via API

## Scaling

* Scaling up compute instance, need a restart (typically a few minutes)
* Disk, can increase size of the database, can not decrease

## Replication

* Read replica - scale horizontally to support more read operations
* Failover replica - can promote and disable replication. Survives zone failure

## Backup & restore

* Automated daily backup
  * Configure backup window
  * Keeps snapshots for seven days on a rolling window
  * Backup in incremental, typically takes a few seconds

* Manual data export to cloud storage (good fit for Nearline storage class)

## Limitations

* Latency & throughput: Relational database - slower with more data, not high throughput
* Not as flexible
  * Can not pick a different database, other than MySQL and PostgreSQL
  * Can not pick specific version
  * Features like multimaster or circular replication not available

# Pricing

CPU + Memory + Storage.

Might make more sense to hire DB administrator to manage database on top of Compute Engine in very large scale.


# When to Use

* Existing on-premis database migrations.
* Common RDBMS workloads.
