# Configuration

The following table lists the configurable parameters of the fluent-logshipping-controller chart, its dependencies and default values.

| Parameter                                             | Description                                                                       | Default           |
| ----------------------------------------------------- | --------------------------------------------------------------------------------- | ----------------- |
| `fluentbit.port`                                      | fluentbit port                                                                    | `5170`            |
| `fluentbit.protocol`                                  | fluentbit protocol                                                                | `TCP`             |
| `fluentbit.userID`                                    | fluentbit user ID                                                                 | `1000`            |
| `fluentbit.groupID`                                   | fluentbit group ID                                                                | `1000`            |
| `fluentbit.logLevel`                                  | log level collected by fluentbit                                                  | `info`            |
| `fluentbit.flushFrequencyInSeconds`                   | Number of seconds between flushes to the forwards                                 | `5`               |
| `fluentbit.memBufferLimit`                            | Size of the memory buffer limit                                                   | `10MB`            |
| `fluentbit.backlogMemLimit`                           | Backlog Memory Limit                                                              | `50M`             |
| `fluentbit.storageMaxChunksUp`                        | Maximum number of chunks to consider `up` in memory                               | `128`             |
| `fluentbit.inputStorageTypes.{}`                      | Defined for each input type, determines what storage to use for buffers. Valid values are `memory` or `filesystem` | `memory` |
| `outputs.name`                                        | outputs deployment name                                                           | `outputs`         |
| `outputs.replicas`                                    | outputs replicas                                                                  | `2`               |
| `outputs.port`                                        | outputs port                                                                      | `24224`           |
| `outputs.protocol`                                    | outputs protocol                                                                  | `TCP`             |
| `outputs.aws.region`                                  | outputs AWS region                                                                 | `eu-central-1`    |
| `outputs.aws.cloudWatch.enabled`                      | Enable CloudWatch plugin                                                          | `false`           |
| `outputs.aws.cloudWatch.logGroupName`                 | outputs CloudWatch plugin log group name                                          | `my-cluster`      |
| `outputs.aws.cloudWatch.logStreamName`                | outputs CloudWatch plugin log stream name                                         | `example-stream`  |
| `outputs.aws.S3.enabled`                              | Enable S3 plugin                                                                  | `false`           |
| `outputs.aws.S3.bucketName`                           | outputs S3 plugin bucket name                                                     | `my-cluster-logs` |
| `outputs.aws.S3.bucketPathPrefix`                     | outputs S3 path in the bucket                                                      | ``    |
| `outputs.elasticsearch.enabled`                       | Enable Elasticsearch plugin                                                       | `false`           |
| `outputs.elasticsearch.host`                          | List of Elasticsearch host (host1)                                                | ``                |
| `outputs.elasticsearch.port`                          | Elasticsearch port                                                                | `9200`            |
| `outputs.elasticsearch.tlsEnabled`                    | Elasticsearch tls enabled                                                         | `true`            |
| `outputs.elasticsearch.path`                          | Elasticsearch path                                                                | `/`               |
| `outputs.elasticsearch.sslVerify`                     | Elasticsearch verify SSL                                                          | `true`            |
| `outputs.elasticsearch.secured`                       | Enable Elasticsearch login                                                        | `false`           |
| `outputs.elasticsearch.user`                          | Elasticsearch username                                                            | ``                |
| `outputs.elasticsearch.password`                      | Elasticsearch password                                                            | ``                |
| `outputs.elasticsearch.config.audit.kubernetes.indexName` | Elasticsearch kubernetes audit log index name                                     | `audit-kubernetes`|
| `outputs.elasticsearch.config.audit.ssh.indexName`        | Elasticsearch ssh audit log index name                                            | `audit-ssh`       |
| `outputs.elasticsearch.config.containers.indexName`       | Elasticsearch container index name                                                | `kubernetes`      |
| `outputs.elasticsearch.config.syslog.indexName`           | Elasticsearch syslog index name                                                   | `syslog`          |
