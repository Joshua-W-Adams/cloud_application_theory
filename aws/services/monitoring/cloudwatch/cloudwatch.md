# CloudWatch

AWS **metric** based monitoring service. Used for performance monitoring and dashboards.

## Metrics

Metrics as key properties that you want to monitor, such as CPU utilisation, traffic through an ALB etc.

They can be either:
- Default (aws created), or
- Custom (you create)

A metric is structured as follows:

Metric
    dimension
    dimension
    ...

*Note: the timestamp propoerty of a metric can be from 2 weeks in the past to 2 hrs in the future.*

### Custom Metrics

You can create any metric you want bu using the following API call.

```
put-metric-data
```

### Metric Filters

Events can be filtered for some criteria which can subsequently be used to trigger an alarm. See diagram below.

![](./../../../img/cloud_watch_metric_filter.png)

### Monitoring Options

Two options:

- basic monitoring
- detailed monitoring - tracks metric data @ 1 minute intervals

## Alarms

Trigger automatic notifications/alarms from any metric.

An alarm has 3 states
- <span style="color:green">OK</span>
- <span style="color:yellow">INSUFFICIENT_DATA</span>
- <span style="color:red">ALARM</span>

Key properties of an alarm are:
- Period: length in time to analyse a metric
- Target: location to send the alarm **AND** action to perform. e.g. stop, terminate, start EC2. Trigger scaling action, send notification to SNS.

## CloudWatch Events

Intercept events from **every** AWS service (sources). A json payload is created from the event and passed to a target. Targets can be of the following 4 types:

- Compute - EC2, lambda, etc.
- Integration - SQS, SNS, Kinesis
- Orchestration - Codepipeline, step functions
- Maintenance - SSM, EC2 Actions

## Event Bridge

Builds on and extends CloudWatch events.

Divided into 3 aspects:
- Default event BUS: events generated from Cloud watch
- Partner event BUS: pipe in events from 3rd party services (e.g. Auth0, GitHub, etc.)
- Custom event BUS: pipe in events from your applications

```
a BUS is a high-speed internal connection
```

### Schema Registry

Cloud watch can analyse the events in your bus and infer the schema.

## Dashboards

Can create custom dashboard from metrics.

## Logs

Directly send you service and application logs to CloudWatch.

Direct integration with other aws services or custom application logs using the cloudwatch api.

### Agents

An agent is a piece of software that runs on a machine. Its purpose is to communciate with some controlling entity.

#### Logs agent

Classic agent that can only sends logs to cloudwatch with no default metrics included.

#### Unified Agent

New agent which extends the logs agent with default metrics (CPU, RAM, DIsk, Netstat etc.).

## Example

### EC2 Instance Recovery

Clouds watch can monitor an EC2 for excessive CPU utilisation. If this failure is detected an action can be configured to "recover" the EC2 instance. 

**This will recover everything except the storage.** For example

- public IPv4 address
- instance id
- all instance metadata