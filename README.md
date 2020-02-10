
[![CircleCI](https://circleci.com/gh/giantswarm/fluent-logshipping-app.svg?style=shield)](https://circleci.com/gh/giantswarm/fluent-logshipping-app)

# Fluent log shipping app

Fluent log shipping app is a managed app proposed to help customers forward logs to any supported [data sinks](#Currently_supported_sinks). 
It contains two parts: 
- A fluentbit daemonset: Small collector running on every node collecting containers and audit logs and for forwarding them to fluentd.
- A fluentd deployment: Takes care of persisting the logs to any data sink

## Requirements

- You can install only one release of this chart per kubernetes cluster
- By default any forward is active so make sure you check [configuration document](helm/fluent-logshipping-app/Configuration.md) before deploy it in your cluster.

## Installation

The logging forwarding app is built to be installed in AWS or Azure. For AWS support to send the logs to S3 and/or Cloudwatch. For Azure it uses Log Analytics:

```text
helm install --namespace logging giantswarm-playground-catalog/fluent-logshipping-app --set fluentd.aws.cloudWatch.enabled=true 
```

## Currently supported sinks

AWS:
- CloudWatch
- S3

Azure:
- Log Analytics

## Configuration

Configuration options are documented in [Configuration.md](helm/fluent-logshipping-app/Configuration.md) document.

## Compatibility

Tested on Giant Swarm release 11.0.0 on `AWS` and `Azure` (Kubernetes 1.16.3).
