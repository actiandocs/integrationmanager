# Worker Configuration

By default, Integration Manager fully embeds the Job Execution Service
within the application. This is meant to facilitate a quick start
experience. For distributed and production environments, it is likely
you will want more control over how the services are deployed,
including, but not limited to:

- Externalizing the Worker Service and Messaging Broker

- Running multiple Workers for additional workload bandwidth

- Running multiple Workers to support workload segregation

## Externalizing the Worker Service and Messaging Broker

For convenience, a set of distributed services is already installed with
Integration Manager. You may enable the basic externalized configuration
by performing the following steps:

- Go to the services console and \*\*Stop\*\* Actian Integration
  Manager.

<!-- end list -->

- Go to ../Actian/IntegrationManager/conf and open
  application.properties.

<!-- end list -->

- Find the entry named "worker.embedded" and change the value to
  "false".

<!-- end list -->

- Go back to the services console:

<!-- end list -->

- > \*\*Start\*\* Actian Messaging Broker.

<!-- end list -->

- > \*\*Start\*\* Actian DataCloud Worker.

<!-- end list -->

- > \*\*Start\*\* Actian Integration Manager.

To revert to the fully embedded configuration

- Go to the services console:

<!-- end list -->

- > \*\*Stop\*\* Actian Messaging Broker.

<!-- end list -->

- > \*\*Stop\*\* Actian DataCloud Worker.

<!-- end list -->

- > \*\*Stop\*\* Actian Integration Manager.

<!-- end list -->

- Go to ../Actian/IntegrationManager/conf and open
  application.properties.

<!-- end list -->

- Find the entry named "worker.embedded" and change the value to
  "true".

<!-- end list -->

- Go back to the services console and \*\*Start\*\* Actian Integration
  Manager.

## Running Multiple Workers for Additional Workload Bandwidth

If you are using an externalized configuration, you can also run
multiple Workers on different machines with network connectivity to the
messaging broker. When multiple Workers are configured, they will
compete for any work on the default job queue. You can enable this by
performing the following steps:

- Download and install the Worker Service on the desired machine or
  VM.

<!-- end list -->

- Go to ../Actian/IntegrationManager/conf and open
  application.properties.

<!-- end list -->

- Find the entry named "queue.host" and change the value from
  "localhost" to the IP address or fully qualified domain name of the
  machine hosting the messaging broker.

<!-- end list -->

- Go to the services console and \*\*Start\*\* Actian DataCloud
  Worker.

## Running Multiple Workers to Support Workload Segregation

In some cases, you may want to segregate workloads based on workload
type or customer type, for example, short versus long running
integration jobs. You can segregate Workloads by creating multiple
Destinations, which are configurations for Worker Pools. You can enable
this by performing the following steps:

- Create a new Destination record within your configuration database.

<!-- end list -->

- Download and install the Worker Service on the desired machine or
  VM.

<!-- end list -->

- Go to ../Actian/IntegrationManager/conf and open
  application.properties.

<!-- end list -->

- Find the entry named "queue.host" and change the value from
  "localhost" to the IP address or fully qualified domain name of the
  machine hosting the messaging broker.

<!-- end list -->

- Find the entry named "worker.destinationId" and set the value to the
  ID field of the Destination record you created in Step 1.

<!-- end list -->

- Go to the services console and \*\*Start\*\* Actian DataCloud
  Worker.
