# Configuration

The following table lists the configurable parameters of the fluent-logshipping-controller chart, its dependencies and default values.

Parameter                                | Description                                        | Default
---------------------------------------- | -------------------------------------------------- | ---
`fluentbit.name`                         | fluentbit deployment name                          | `fluent-bit`
`fluentbit.port`                         | fluentbit port                                     | `5170`
`fluentbit.protocol`                     | fluentbit protocol                                 | `TCP`
`fluentbit.userID`                       | fluentbit user ID                                  | `1000`
`fluentbit.groupID`                      | fluentbit group ID                                 | `1000`
`fluentbit.initUserID`                   | fluentbit user ID for init container               | `0`
`fluentbit.initGroupID`                  | fluentbit group ID for init container              | `0`
`fluentbit.logLevel`                     | log level collected by fluentbit                   | `info`
`fluentd.name`                           | fluentd deployment name                            | `fluentd`
`fluentd.replicas`                       | fluentd replicas                                   | `2`
`fluentd.port`                           | fluentd port                                       | `24224`
`fluentd.protocol`                       | fluentd protocol                                   | `TCP`
`fluentd.aws.cloudWatch.enabled`         | fluentd CloudWatch plugin enabled                  | `false`
`fluentd.aws.cloudWatch.region`          | fluentd CloudWatch plugin region                   | `eu-central-1`
`fluentd.aws.cloudWatch.logGroupName`    | fluentd CloudWatch plugin log group name           | `my-cluster`
`fluentd.aws.cloudWatch.logStreamName`   | fluentd CloudWatch plugin log stream name          | `example-stream`
`fluentd.aws.S3.enabled`                 | fluentd S3 plugin enabled                          | `false`
`fluentd.aws.S3.bucketName`              | fluentd S3 plugin bucket name                      | `my-cluster-logs`
`fluentd.aws.S3.bucketRegion`            | fluentd S3 plugin region                           | `eu-central-1`
`fluentd.aws.S3.bucketPathPrefix`        | fluentd S3 plugin prefix                           | `gs-`
`fluentd.aws.S3.account`                 | fluentd S3 plugin default account of the S3 bucket | `0000000000`
`fluentd.aws.S3.role`                    | fluentd S3 plugin default role name to assume      | `my-role`
`fluentd.azure.logAnalytics.enabled`     | fluentd Azure Log Analytics plugin enabled         | `false`
`fluentd.azure.logAnalytics.workspaceId` | fluentd Azure Log Analytics plugin workspace id    | `workspace_id`
`fluentd.azure.logAnalytics.sharedKey`   | fluentd Azure Log Analytics plugin shared key      | `shared_key`
`giantswarm.monitoring.enabled`          | giantswarm monitoring support                      | `true`
