# Google Stackdriver

[Google Stackdriver](https://cloud.google.com/stackdriver/) provides Monitoring, logging, and diagnostics (tracing & debugging) for applications on __GCP__, __AWS__ and __on-premise__ resources.

## Features

* Monitor Google Cloud Platform, AWS and on-premise resources.
* Find and fix issues fast.
* Full-stack insights.
* Native Google integration.
* Metrics explorer enables monitoring resources without creating charts.
* Daily or weekly reports via email

## Stackdriver Organization

* Managed under one account.
* Hosted under one Project.
* Monitor many Projects.
* Consider making a Project purely to host the Stackdriver account.

## Partner Integrations

* Partners with:
  * BMC
  * Splunk
  * PagerDuty
  * logentries
  * Tenable Network Security
  * Atlassian Hipchat
  * Netskope

## Monitoring

* Create Dashboards, Charts, and Alerts.
* Uptime and health checks.
* Monitoring agent (monitoring agent & logging agent) installed into VMs.
* Custom metrics can be added to your code. Two ways to create custom metrics:
  * OpenCensus
  * StackDriver's monitoring API

### Uptime Monitoring

Condition => Incident => Notification

* Conditions can be based on Metrics or Conditionals.
* Notifications include:
  * Email.
  * SMS.
  * Webhook.
  * 3rd Party.
  * PagerDuty, HipChat, Campfire, Slack, etc.

## Groups

* Aggregate metrics across a set of machines.
  * Dynamically defined.
  * Useful for high change environments.
* Separate production from dev.
* Filter GKE data by name and custom tags for cluster.

## Alerts

* Alert on symptoms not causes (eg: monitor failing queries not databases going down).
* Avoid a single point of failure in your alert strategy.
* Customize alerts.
* Avoid noise.
* __Policy__ consists of conditions that determine when to issue an alert or notification.
* A policy can have one or more __notification channels__
* __Documentation__ helps devops engineer understand the problem and provide information on how to solve the issue

## Logging - Managed service

* Platform, system, and application logs.
  * Public API to write to logs.
  * 30 day retention with option to transfer to Cloud Storage.
* Search, view, and filter.
* Log-based metrics.
* Monitoring alerts can be set on log events.
* Data can be exported to BigQuery, Cloud Storage, Cloud Pub/Sub, or Custom.
* Export only applies to new logs after it is configured.

_Note: Agent needs to be installed for application logs._

## Error Reporting

* Aggregate and display errors for running cloud services including:
  * Error notifications.
  * Error dashboards.
  * Code including Java, Python, JavaScript, Ruby, C#, PHP, and Go.

## Tracing - Cloud Trace

Cloud Trace is a distributed tracing system for collecting latency data from an application.

* Near real time.
* Latency reporting including data from:
  * Google App Engine.
  * Google HTTP(S) load balancers.
  * Applications instrumented with Stackdriver Trace SDKs.
* Per-URL latency sampling.

## Debugging - Cloud Debugger

Cloud Debugger allows developers to inject log messages on the fly without altering source code or take snapshots of the state of an application.

* Inspect an application without stopping it or slowing it down significantly.
* Cloud App Engine Standard or Flexible.
* Java, Python, or Go.
* Debug snapshots (capture call stack and local variables).
* Debug logpoints (inject logging into a service without stopping it).
