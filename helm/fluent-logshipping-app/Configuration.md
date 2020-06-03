# Configuration

The following table lists the configurable parameters of the fluent-logshipping-controller chart, its dependencies and default values.

| Parameter                                             | Description                                                                       | Default           |
| ----------------------------------------------------- | --------------------------------------------------------------------------------- | ----------------- |
| `fluentbit.name`                                      | fluentbit deployment name                                                         | `fluent-bit`      |
| `fluentbit.port`                                      | fluentbit port                                                                    | `5170`            |
| `fluentbit.protocol`                                  | fluentbit protocol                                                                | `TCP`             |
| `fluentbit.userID`                                    | fluentbit user ID                                                                 | `1000`            |
| `fluentbit.groupID`                                   | fluentbit group ID                                                                | `1000`            |
| `fluentbit.logLevel`                                  | log level collected by fluentbit                                                  | `info`            |
| `fluentbit.flushFrequencyInSeconds`                   | Number of seconds between flushes to the forwards                                 | `5`               |
| `fluentd.name`                                        | fluentd deployment name                                                           | `fluentd`         |
| `fluentd.replicas`                                    | fluentd replicas                                                                  | `2`               |
| `fluentd.port`                                        | fluentd port                                                                      | `24224`           |
| `fluentd.protocol`                                    | fluentd protocol                                                                  | `TCP`             |
| `fluentd.aws.kiam`                                    | Kiam support                                                                      | `false`           |
| `fluentd.aws.cloudWatch.enabled`                      | Enable CloudWatch plugin                                                          | `false`           |
| `fluentd.aws.cloudWatch.region`                       | fluentd CloudWatch plugin region                                                  | `eu-central-1`    |
| `fluentd.aws.cloudWatch.logGroupName`                 | fluentd CloudWatch plugin log group name                                          | `my-cluster`      |
| `fluentd.aws.cloudWatch.logStreamName`                | fluentd CloudWatch plugin log stream name                                         | `example-stream`  |
| `fluentd.aws.S3.enabled`                              | Enable S3 plugin                                                                  | `false`           |
| `fluentd.aws.S3.bucketName`                           | fluentd S3 plugin bucket name                                                     | `my-cluster-logs` |
| `fluentd.aws.S3.bucketRegion`                         | fluentd S3 plugin region                                                          | `eu-central-1`    |
| `fluentd.aws.S3.bucketPathPrefix`                     | fluentd S3 plugin prefix                                                          | `gs-`             |
| `fluentd.aws.S3.account`                              | fluentd S3 plugin default account of the S3 bucket                                | `0000000000`      |
| `fluentd.aws.S3.role`                                 | fluentd S3 plugin default role name to assume                                     | `my-role`         |
| `fluentd.azure.logAnalytics.enabled`                  | Enable Azure Log Analytics plugin                                                 | `false`           |
| `fluentd.azure.logAnalytics.workspaceId`              | Azure Log Analytics plugin workspace id ([where do I find it?](Azure.md))         | ``                |
| `fluentd.azure.logAnalytics.sharedKey`                | Azure Log Analytics plugin shared key ([where do I find it?](Azure.md))           | ``                |
| `fluentd.elasticsearch.enabled`                       | Enable Elasticsearch plugin                                                       | `false`           |
| `fluentd.elasticsearch.host`                          | List of Elasticsearch host (host1)                                                | ``                |
| `fluentd.elasticsearch.port`                          | Elasticsearch port                                                                | `9200`            |
| `fluentd.elasticsearch.tlsEnabled`                    | Elasticsearch tls enabled                                                         | `true`            |
| `fluentd.elasticsearch.path`                          | Elasticsearch path                                                                | `/`               |
| `fluentd.elasticsearch.sslVerify`                     | Elasticsearch verify SSL                                                          | `true`            |
| `fluentd.elasticsearch.secured`                       | Enable Elasticsearch login                                                        | `false`           |
| `fluentd.elasticsearch.user`                          | Elasticsearch username                                                            | ``                |
| `fluentd.elasticsearch.password`                      | Elasticsearch password                                                            | ``                |
| `fluentd.elasticsearch.indices.audit.kubernetes.name` | Elasticsearch kubernetes audit log index name                                     | `audit-kubernetes`|
| `fluentd.elasticsearch.indices.audit.ssh.name`        | Elasticsearch ssh audit log index name                                            | `audit-ssh`       |
| `fluentd.elasticsearch.indices.containers.name`       | Elasticsearch container index name                                                | `kubernetes`      |
| `fluentd.elasticsearch.indices.syslog.name`           | Elasticsearch syslog index name                                                   | `syslog`          |
| `giantswarm.monitoring.enabled`                       | Giantswarm monitoring support                                                     | `true`            |