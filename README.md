
[![CircleCI](https://circleci.com/gh/giantswarm/fluent-logshipping-app.svg?style=shield)](https://circleci.com/gh/giantswarm/fluent-logshipping-app)

# Fluent log shipping app

Fluent log shipping app is a managed app used to help customers forward their logs to any supported [storage backends](#currently-supported-storage-backends).

It is made of two components: 
- A [fluent-bit](https://github.com/fluent/fluent-bit) DaemonSet: Lightweight log collector used to collect and forward containers and audit logs to the fluentd Deployment.
- A [fluentd](https://github.com/fluent/fluentd) Deployment: Takes care of persisting the logs to any of the configured storage backends.

## Requirements

- You can install only one release of this chart per kubernetes cluster
- By default, no forwarding is active so make sure you check [configuration document](helm/fluent-logshipping-app/Configuration.md) before deploying it in your cluster.

## Currently supported storage backends

### AWS 

- [CloudWatch](https://aws.amazon.com/cloudwatch/)
- [S3](https://aws.amazon.com/s3/)

### Azure

- [Log Analytics](https://azure.microsoft.com/en-us/services/monitor)

### Others

- [Elasticsearch](https://www.elastic.co/elasticsearch/)

## Installation

The log shipping app is built to be installed in AWS or Azure.

Sample command for installing it on AWS with cloudwatch enabled:

```text
helm install --namespace logging giantswarm-playground-catalog/fluent-logshipping-app --set fluentd.aws.cloudWatch.enabled=true 
```

## Exported logs

The app currently exports the following logs:

| Log type              | Location                       | Format            |
| --------------------- | -------------------------------| ----------------- |
| Container Logs        | `/var/log/containers/*.log`    | `json`            |
| Kubernetes Audit Log  | `/var/log/apiserver/audit.log` | `json`            |
| SSH Access Logs       | `syslog`                       | `^\<(?<pri>[0-9]+)\>(?<time>[^ ]* {1,2}[^ ]* [^ ]*) (?<host>[^ ]*) (?<ident>[a-zA-Z0-9_\/\.\-]*)(?:\[(?<pid>[0-9]+)\])?(?:[^\:]*\:)? *(?<message>.*)$` |

## Configuration

Configuration options are documented in [Configuration.md](helm/fluent-logshipping-app/Configuration.md) document.

## Compatibility

Tested on Giant Swarm release 11.0.0 on `AWS` and `Azure` (Kubernetes 1.16.3).
