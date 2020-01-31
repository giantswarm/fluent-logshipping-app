
[![CircleCI](https://circleci.com/gh/giantswarm/fluent-logshipping-app.svg?style=shield)](https://circleci.com/gh/giantswarm/fluent-logshipping-app)

# Fluent log shipping app

Fluent log shipping app is a managed app proposed to help customers forward logs to any supported [data sinks](#Currently_supported_sinks). 
It contains two parts: 
- A fluentbit daemonset: Small collector running on every node collecting containers and audit logs and for forwarding them to fluentd.
- A fluentd deployment: Takes care of persisting the logs to any data sink

## Currently supported sinks

AWS: 
- CloudWatch
- S3

Azure:
- Log Analytics

## Configuration

Configuration options are documented in [Configuration.md](helm/fluent-logshipping-app/Configuration.md) document.
