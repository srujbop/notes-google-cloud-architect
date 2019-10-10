# Cloud Storage

[Cloud Storage](https://cloud.google.com/storage/docs/storage-classes) is an internet-scale immutable BLOB (unstructured) store.

Similar to Amazon __S3__

Think of image, user content (profile photo, voice recording), data archival, 

Automtically replicated and caching around the world

## Features

* Unlimited storage scalable to exabytes of data. __Scale, speed, throughput, durability__
* Single API across storage classes.
* Data encrypted in-flight and at rest.
* 11 nines durability through erasure coding.
* Object versioning. Overitting data doesn't truely overwrite the original data
* Object change notification.
* Access logging.
* Lifecycle management. Conditionally delete data automatically
  * Per-object age
  * Fixed date cut-off
  * Version history
  * Latest version
* Per-object storage classes.
* Composite objects and parallel uploads: compose up to 32 existing objects into a new object without transferring additional object data.

__Note:__ Availability refers to system uptime where as durability refers to long-term data protection.

## Bucket Default Storage Classes

Content is stored in Buckets that contain a __globally__ unique name, a location, and a default storage class. If you do not specify a default storage class you will see the bucket listed as Standard Storage in the API. Objects stored in a Standard Storage bucket will be regional or mulit-regional depending on where the bucket is stored.

Storeage classes only apply to the objects within Cloud Storage, not the Buckets. You can change the storage class of an object or a bucket. Changing the storage class of a bucket will only affect new objects.

All storage classes offer the same throughput, low latency, and high durability.

Different storage classes are about __performance__, __availability__, __price__, but never about __durability__.

### Multi-Regional Storage

Use Multi-Regional Storage for storing data that is frequently accessed ("hot" objects) around the world, such as serving website content, streaming videos, or gaming and mobile applications.

* 99.95% availability.
* Geo-redundant.

### Regional Storage

Use Regional Storage for storing content frequently accessed in the same region as your Google Cloud DataProc or Google Compute Engine instances that use it, such as for data analytics. Replicated across different zones inside a single region

* 99.9% availability.
* Lower cost per GB stored.
* Data stored in a narrow geographic region.
* Redundant across availability zones.

### Nearline Storage

Use Nearline Storage for data you do not expect to access frequently (i.e., no more than once per month). Ideal for back-up and serving long-tail multimedia content. Poor choice for anything customer facing.

* 99.0% availability.
* Higher latency to first byte
* Very low cost per GB stored.
* Data retrieval costs.
* Higher per-operation costs.
* 30-day minimum storage duration.

### Coldline Storage

Use Coldeline Storage for data you expect to access infrequently (i.e., no more than once per year). Typically this is for __disaster recovery__, or data that is archived and may or may not be needed at some future time.

* 99.0% availability.
* Lowest cost per GB stored.
* Data retrieval costs.
* Higher per-operation costs.
* 90-day minimum storage duration.

## Changing Bucket Class

Regional <=> Nearline or Coldline

Nearline (Regional) <=> Regional or Coldline

Coldline (Regional) <=> Regional or Nearline

Multi-Regional <=> Nearline or Coldline
Nearline (Multi-Regional) <=> Multi-Regional or Coldline
Coldline (Multi-Regional) <=> Multi-Regional or Nearline

Creating a Bucket as either Nearline or Coldline will set its location type to Multi-Regional.

## Access Control

* IAM - Broad control but not fine-grained control over object in Buckets.
* ACLs - Control access to individual object on Buckets. Supports Owner, Writer, and Reader permissions. User, group, domain
* Signed URL - Time-limited access with specific operations (GET/PUT/DELETE/POST).
* Signed Policy Documents - Greater control over size, content type, and other upload characteristics than signed URLs.
* Firebase Security Rules - ABAC.

## Object Transfer

* High performance imports of online data.
* Imports from GCP Buckets, S3 Buckets, or Web source.
* Supports schedules, filtering.
* Offline Media Import / Export via third party service providers.

## Limitation

* No object can be larger than 5TB

## Pricing

* Amount of data stored
* Amount of data transferred (traffic that stays inside the same region is free of charge)
* Number of operations executed
