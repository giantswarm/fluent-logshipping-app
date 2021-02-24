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
| `outputs.name`                                        | outputs deployment name                                                           | `outputs`         |
| `outputs.replicas`                                    | outputs replicas                                                                  | `2`               |
| `outputs.port`                                        | outputs port                                                                      | `24224`           |
| `outputs.protocol`                                    | outputs protocol                                                                  | `TCP`             |
| `outputs.aws.kiam`                                    | Kiam support                                                                      | `false`           |
| `outputs.aws.role`                                    | AWS role to assume                                                                | `""`              |
| `outputs.aws.cloudWatch.enabled`                      | Enable CloudWatch plugin                                                          | `false`           |
| `outputs.aws.cloudWatch.region`                       | outputs CloudWatch plugin region                                                  | `eu-central-1`    |
| `outputs.aws.cloudWatch.logGroupName`                 | outputs CloudWatch plugin log group name                                          | `my-cluster`      |
| `outputs.aws.cloudWatch.logStreamName`                | outputs CloudWatch plugin log stream name                                         | `example-stream`  |
| `outputs.aws.S3.enabled`                              | Enable S3 plugin                                                                  | `false`           |
| `outputs.aws.S3.bucketName`                           | outputs S3 plugin bucket name                                                     | `my-cluster-logs` |
| `outputs.aws.S3.bucketRegion`                         | outputs S3 plugin region                                                          | `eu-central-1`    |
| `outputs.aws.S3.bucketPathPrefix`                     | outputs S3 plugin prefix                                                          | `gs-`             |
| `outputs.aws.S3.account`                              | outputs S3 plugin default account of the S3 bucket                                | `0000000000`      |
| `outputs.aws.S3.role`                                 | outputs S3 plugin default role name to assume                                     | `""`              |
| `outputs.azure.logAnalytics.enabled`                  | Enable Azure Log Analytics plugin                                                 | `false`           |
| `outputs.azure.logAnalytics.workspaceId`              | Azure Log Analytics plugin workspace id ([where do I find it?](Azure.md))         | ``                |
| `outputs.azure.logAnalytics.sharedKey`                | Azure Log Analytics plugin shared key ([where do I find it?](Azure.md))           | ``                |
| `outputs.elasticsearch.enabled`                       | Enable Elasticsearch plugin                                                       | `false`           |
| `outputs.elasticsearch.host`                          | List of Elasticsearch host (host1)                                                | ``                |
| `outputs.elasticsearch.port`                          | Elasticsearch port                                                                | `9200`            |
| `outputs.elasticsearch.tlsEnabled`                    | Elasticsearch tls enabled                                                         | `true`            |
| `outputs.elasticsearch.path`                          | Elasticsearch path                                                                | `/`               |
| `outputs.elasticsearch.sslVerify`                     | Elasticsearch verify SSL                                                          | `true`            |
| `outputs.elasticsearch.secured`                       | Enable Elasticsearch login                                                        | `false`           |
| `outputs.elasticsearch.user`                          | Elasticsearch username                                                            | ``                |
| `outputs.elasticsearch.password`                      | Elasticsearch password                                                            | ``                |
| `outputs.elasticsearch.indices.audit.kubernetes.name` | Elasticsearch kubernetes audit log index name                                     | `audit-kubernetes`|
| `outputs.elasticsearch.indices.audit.ssh.name`        | Elasticsearch ssh audit log index name                                            | `audit-ssh`       |
| `outputs.elasticsearch.indices.containers.name`       | Elasticsearch container index name                                                | `kubernetes`      |
| `outputs.elasticsearch.indices.syslog.name`           | Elasticsearch syslog index name                                                   | `syslog`          |
| `giantswarm.monitoring.enabled`                       | Giantswarm monitoring support                                                     | `true`            |
