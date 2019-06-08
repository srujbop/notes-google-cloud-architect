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

# Google Cloud Architect Notes

This repository contains my notes for studying the Google Cloud Platform to sit the Cloud Architect exam.

I passed the exam and am leaving this repository here for anyone else to use.

Either fork this repository or raise an issue and I will make you a contributor.

__These notes have not been proof read or polished in any way. They are accurate as of March 2018.__

## Index

* [Acronyms](/Acronyms.md)
* [Build PDF](#build-pdf)
* [PDF Version](/pdf)
* [Overview](/Overview.md)
* [Courses](/Courses.md)
* [Management](/Management.md)
* [Products and Services](#products-and-services)
* [References](/References.md)
* [Study Plan](/Study%20Plan.md)

## Products and Services

* [Products and Services](Products%20and%20Services.md)
* [Big Data](/Big%20Data)
* [Cloud AI](/Cloud%20AI)
* [Compute](/Compute)
* [Design](/Design)
* [Diagrams](/Diagrams)
* [Networking](/Networking)
* [Resource Manager](/Resource%20Manager)
* [Storage](/Storage)
* [Tools](/Tools)

## Build PDF

These notes can be built into PDF (or any format for that matter) to make it easier to read and review.

There is a pre-built set of PDF documents in the [pdf](/pdf) directory.

### How to build on Windows

If you wish to build the documents yourself there is a PowerShell script in the root of the repository called [ConvertTo-PDF](/ConvertTo-PDF.ps1).

1. Install [pandoc](http://pandoc.org/) if it is not already installed.
1. Install [MikTex](https://miktex.org/) if it is not already installed.
1. Clone this repository using [git](https://git-scm.com/).
1. Open a PowerShell console.
1. Change directory to the root of the repository.
1. Run the PowerShell script by typing `.\ConvertTo-PDF.ps1`.

The script will delete the current `pdf` directory and then recreate it by building the documents from the markdown files.
