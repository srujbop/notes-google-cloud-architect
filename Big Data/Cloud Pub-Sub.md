# Google Cloud Pub/Sub

[Google Cloud Pub/Sub](https://cloud.google.com/pubsub/docs/overview) is a fully managed messaging system (like Kafka). It brings the scalability, flexibility, and reliability of enterprise message-oriented middleware to the cloud.

## Features

* Scalable, reliable messaging.
* Supports many-to-many asynchronous messaging.
* Includes support for offline consumers.
* Based on proven Google technologies.
* Integrates with Cloud Dataflow for data processing pipelines.
* Uses push/pull subscriptions to topics.

## Concepts

* Topics
* Messages - payload is always base-64-encoded, atttributes are not
* Subscription - referred as __queues__ in other messaging systems
* Acknowledge deadline

* Producer --> Tpoic --> Subscription --> Consumer
* Pull subscription vs Push subscription (call back handler)
* Fan-out broadcast messaging vs Work-queue messaging (distributing work)
