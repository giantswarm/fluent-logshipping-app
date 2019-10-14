
[![CircleCI](https://circleci.com/gh/giantswarm/logging-app.svg?style=svg)](https://circleci.com/gh/giantswarm/logging-app)

# Logging App

Logging app is a proposed managed app to help customers forward logs to AWS CloudWatch or S3. It contains two parts: fluentbit is a small collector running as daemonset in the clusters and forwarding the logs to fluentd which actually takes care of persisting the logs to a third party service like S3 or CloudWatch.

## Configuration

The following table lists the configurable parameters of the fluentd chart and their default values.

Parameter | Description | Default
--- | --- | ---
`fluentbit.name` | fluentbit deployment name | `fluentbit`
`fluentbit.port` | fluentbit port | `2020`
`fluentbit.protocol` | fluentbit protocol | `TCP`
`fluentbit.userID` | fluentbit user ID | `1000`
`fluentbit.groupID` | fluentbit group ID | `1000`
`fluentbit.inituserID` | fluentbit user ID  for init container| `0`
`fluentbit.initgroupID` | fluentbit group ID for init container | `0`
`fluentd.name` | fluentd deployment name | `fluentd`
`fluentd.replicas` | fluentd replicas | `2`
`fluentd.port` | fluentd port | `24224`
`fluentd.protocol` | fluentd protocol | `TCP`
`fluentd.cloudWatch.enabled` | fluentd cloudWatch plugin enabled | `true`
`fluentd.cloudWatch.region` | fluentd cloudWatch plugin region | `eu-central-1`
`fluentd.cloudWatch.logGroupName` | fluentd cloudWatch plugin log group name | `my-cluster`
`fluentd.cloudWatch.logStreamName` | fluentd cloudWatch plugin log stream name | `example-stream`
`fluentd.S3.enabled` | fluentd S3 plugin enabled | `true`
`fluentd.S3.bucketName` | fluentd S3 plugin bucket name | `my-cluster-logs`
`fluentd.S3.bucketRegion` | fluentd S3 plugin region | `eu-central-1`
`fluentd.S3.bucketPathPrefix` | fluentd S3 plugin prefix | `gs-`
`fluentd.S3.account` | fluentd S3 plugin default account of the S3 bucket | `0000000000`
`fluentd.S3.role` | fluentd S3 plugin default role name to assume | `my-role`
