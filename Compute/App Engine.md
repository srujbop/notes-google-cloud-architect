# App Engine

App Engine is a PaaS for building scalable web applications and mobile backends.

App Engine Standard Environment vs App Engine Flex

App Engine manages the hardware, networking infrastructure, load balancing, monitoring and scaling, required to run your code.

__Auto scaling__ is a key selling point.

## Standard Environment

Your code inside a __sandbox__.

The App Engine standard environment is based on container instance running in Google's infrastructure.
The containers used in the Standard Environment are specific to Google. Google provides runtimes for Java, Node.JS, Python, PHP and Go. Limited to these popular programing languages

Sandbox constraints:

* No writing to local file system.
* Request timeouts at 60 seconds.
* Limit on 3rd-party software installations.

## Flexible Environment

Your code running in __Docker__ containers.

You would choose the flexible environment when your applications need more flexibility than the standard environment.

Pricing is based on Compute Engine usage.

## Standard vs Flexible

|                     | Standard Environment     | Flexible Environment |
|---------------------|--------------------------|----------------------|
| Instance startup    | Milliseconds             | Minutes              |
| SSH Access          | No                       | Yes (not default)    |
| Scaling             | Manual, Basic, Automatic | Manual, Automatic    |
| Write to local disk | No                       | Yes (ephemeral)      |
| 3rd Pty Bin Support | No                       | Yes                  |
| Network Access      | Via App Engine Services  | Yes                  |
| Customizable Stack  | No                       | Yes                  |

## Concepts

Application, Service, Version, Instance

One project is limited to one application (one project, one purpose)

One application can have multile services

One service can have multiple versions

Instance - an abstract chunk of CPU and memory available to run the application inside a sandbox.

The lightweight sanbox allows your application to scale from zero to thousands of instances very quickly.

URL: version.service.your-project-id.appspot.com

## Deployment

gcloud app deploy

promite_by_default

## Scaling

App Engine Standard

* Automatic Scaling
  * idle instances (min, max instances that can sit idle)
  * pending latency (min, max time any given request should spend sitting in the queue)
  * concurrent requests (default 8, can go up to 80)

* Basic Scaling
  * max number of instances
  * how long to keep an idel instance before turning it off

* Manual Scaling - configure exactly the number of instances

App Engine Flex

* Automatic Scaling
  * Number of instances (min, max) - limited to 20 by default, 
  * CPU utilization target - aim for 50% utilization across all running instances
  * cooldown period - 2 minutes by default

* Manual Scaling - configure exactly the number of instances

> Basic Scaling - A service with basic scaling will create an instance when the application receives a request. The instance will be turned down when the app becomes idle. Basic scaling is ideal for work that is intermittent or driven by user activity.

## Instance class

F1, F2, F4, F4_1G

Larger class can handle more concurrent requests

## App Engine Standard's Managed Services

* Store data with Cloud Datastore - nonrelational storage system, auto authentication, no dependency to install
* Memcached service - shared service, some limitations
* Deferring tasks with Task Queues
* Traffic spliting - A/B testing
