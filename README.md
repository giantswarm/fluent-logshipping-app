[![CircleCI](https://dl.circleci.com/status-badge/img/gh/giantswarm/fluent-logshipping-app/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/giantswarm/fluent-logshipping-app/tree/master)

# Fluent log shipping app

Fluent log shipping app is a managed app used to help customers forward their logs to any supported [storage backends](#currently-supported-storage-backends).
It use [fluent-bit](https://github.com/fluent/fluent-bit) DaemonSet, a lightweight log collector used to collect and forward containers and audit logs your chosen output

## Requirements

- You can install only one release of this chart per kubernetes cluster
- By default, no forwarding is active so make sure you check [configuration document](helm/fluent-logshipping-app/Configuration.md) before deploying it in your cluster.

## Currently supported storage backends

### AWS

- [CloudWatch](https://aws.amazon.com/cloudwatch/)
- [S3](https://aws.amazon.com/s3/)

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

## AWS

### Prerequisites

- When using Cloudwatch or S3 a new role has to be created upfront which allows pushing of the logs to the backend(s). More info about permissions in official docs ([S3](https://github.com/fluent/fluent-plugin-s3#iam-policy), [CloudWatch](https://github.com/fluent-plugins-nursery/fluent-plugin-cloudwatch-logs#preparation)).
- When using S3 as an ouput for logs in the Management Cluster make sure to include "-g8s-" in the name of the bucket or modify the S3 VPC endpoint to allow a different name, otherwise you will get an Unauthorized error.

## Compatibility

Tested on Giant Swarm release 11.0.0 on `AWS` and `Azure` (Kubernetes 1.16.3).
