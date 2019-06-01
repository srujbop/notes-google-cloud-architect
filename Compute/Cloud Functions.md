# Google Cloud Functions

[Google Cloud Functions](https://cloud.google.com/functions/docs/concepts/overview) is a serverless execution environment for building and connecting cloud services. Glue

Allows you to write functions in JavaScript and manage dependencies like you would for a typical Node.js application.

With Cloud Functions you write simple, single-purpose functions that are attached to events emitted from your cloud infrastructure and services. Your Cloud Function is triggered when an event being watched is fired. Your code executes in a fully managed environment. There is no need to provision any infrastructure or worry about managing any servers.

## Features

* Event-based microservices.
* Execute in a fully managed, serverless, Node.js environment.
* Connect and extend cloud services such as Cloud Storage, Cloud Pub/Sub, and more.
* Deploy functions from Cloud Storage Bucket, GitHub or Bitbucket.
* Trigger include Cloud Pub/Sub, HTTP, Cloud Storage.
* Stackdriver integration.

## Concepts

* Event --(trigger)--> Function
  * Cloud storage (uploading, deleting, archiving a file)
  * Cloud pub/sub (publishing a message)
  * HTTP
  * Firebase
  * Stackdriver logging
* Synchronous (request, response) vs asynchronous (event, callback)
* Package code --> Upload to cloud storage --> deploy
* Goolge source repository

## Pricing

* number of invocations
* networking cost
* compute time and memory time
* free-tier

## Limitation

* By default, will time out after one minute
* Timeout can be set as long as 9 minutes

## Runtime environments

* Python 3
* Node.js 6
* Node.js 8

## Deployment

* gcloud functions deploy
  * runtime
  * trigger-resource
  * trigger-event

## Example

A function can be triggered by someone uploading a file to Cloud Storage or a message being published by Cloud Pub/Sub.
