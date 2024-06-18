# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project's packages adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [5.1.1] - 2024-06-18

### Fixed

- Reduce minAllowed cpu from 200 to 50 millicores to avoid allocating unused cpu.

## [5.1.0] - 2024-06-12

### Added

- Add priorityClass to the daemonset.

## [5.0.0] - 2024-05-28

### Changed

- Upgrade to fluent-bit 3.0.6 to fix some recent CVEs.

## [4.2.0] - 2024-03-25

### Changed

- Add possibility to disable the execve audit logs as they are quite noisy.

## [4.1.0] - 2024-03-08

### Changed

- Add back `kiam` support.

## [4.0.0] - 2024-03-08

### Changed

- Push to `capz-app-collection`
- Configure multiline parser to not split long log lines.
- Allow the use of a PVC instead of an emptyDir to keep the tracked files upon restart.
- Add post processing extra filters and rename the `extraFilters` property into `extraFilters.preprocessing`

### Removed

- Remove deprecated KIAM and role properties support as everything should be using IRSA by now.
- Removed `azure` and `tcp` configuration as it is unused.

## [3.1.2] - 2024-02-04

### Fixed

- Renders resources only if the daemonset is deployed to avoid rendering useless resources like VPA CR.

## [3.1.1] - 2023-12-20

### Changed

- Configure `gsoci.azurecr.io` as the default container image registry.

## [3.1.0] - 2023-12-19

### Changed

- Upgrade to fluent-bit 2.2.0
- Use emptyDir instead of hostPath for filesystem storage type.

## [3.0.2] - 2023-10-02

### Changed

- Add condition for PSP installation in helm chart.

## [3.0.1] - 2023-08-29

### Fixed

- Fix ausearch command to ensure we get all possible command executions.

## [3.0.0] - 2023-07-12

### Changed

- Upgrades fluent-bit to 2.1.6.
- Adds support for ausearch and the exec plugin using a custom image.

## [2.3.3] - 2023-07-05

### Added

- Add service monitor.

## [2.3.2] - 2023-06-28

### Fixed

- Fix cluster role to use latest PSP api group.

## [2.3.1] - 2023-06-27

### Fixed

- Fix Kyverno Policy Exceptions.

## [2.3.0] - 2023-06-27

### Added

- Add Kyverno Policy Exceptions.

### Removed

- Stop pushing to `openstack-app-collection`.

## [2.2.0] - 2023-04-27

### Changed

- Change control-plane node toleration.
- Ensure fluent-logshipping-app will run on 1.25.

## [2.1.0] - 2023-04-13

### Added

- Service Account annotations - e.g. for IRSA

## [2.0.3] - 2023-01-09

### Added

- Add host name to auditd logs.

## [2.0.2] - 2022-11-08

### Changed

- Push to GCP, CAPA and VCD app collections.

## [2.0.1] - 2022-10-12

### Changed

- Update audit log location to use the whole list of audit log files.

## [2.0.0] - 2022-09-28

### Changed

- Support CRI instead of Docker log format.
- Change storage path to not use a tmpfs filesystem to not overload nodes.

## [1.4.0] - 2022-08-04

### Changed

- Use fluent-bit image with aws-for-fluent-bit plugins to be able to configure the log-stream-name and reduce risks of throttling.

## [1.3.0] - 2022-08-02

### Added

- Add VPA support.
- Add container registry domain support to images.
 
### Changed

- Send md5 header for s3 outputs.

## [1.2.0] - 2022-07-11

### Changed

- Support collection of the execve auditd logs

## [1.1.1] - 2022-06-27

### Fixed

- Correct team and config annotations.

## [1.1.0] - 2022-06-27

### Fixed

- Add aws s3 endpoint and access key support.

## [1.0.1] - 2022-05-12

### Fixed

- Fix prometheus metric path in the annotation

## [1.0.0] - 2022-05-11

### Changed

- Downgrade fluent-bit to 1.7.9.

### Fixed

- Fix missing leading slash on s3 bucket prefix.

## [0.7.3] - 2022-04-28

### Fixed

- Fix extra slash in s3 object key format.

## [0.7.2] - 2022-04-28

### Fixed

- Fix s3 object key format.

## [0.7.1] - 2022-04-20

### Fixed

- Move to `log_stream_name` as `log_stream_prefix` is deprecated for the cloudwatch_logs plugin.

## [0.7.0] - 2022-04-19

### Changed

- Upgrade to `fluent-bit v1.9.1`
- Sort out app labels.
- Push to app collections.
- Disable fluentbit if not outputs and inputs are defined.

## [0.6.7] - 2022-04-11

### Fixed

- Fix rbac api version

## [v0.6.6]

- Update app metadata

### Fixed

- Fix an issue with systemd log format, upgrade systemd lib from 241 to 247. see https://github.com/giantswarm/giantswarm/issues/19055

## [v0.6.4]

### Changed

- [Cloudwatch Output] Break up the stream names, this helps prevent hitting API limits

## [v0.6.3]

### Added

- Make Daemonset resources configurable

## [v0.6.2]

### Added

- Flexible Filter and Output, users can specifiy their own filter and outputs.
- More options for back pressure tweaking

## [v0.6.1]

### Added

- [Cloudwatch Output] Use Node name as part of the log stream name

### Fixed

- Correct the output config format for AWS outputs (split them based on input)
- Mount journald path and set it in fluent-bit config

### Changed

- Moved to Giant Swarm default catalogue

## [v0.6.0]

_Note: Jumping to next minor version as we are dropping fluentd_

### Changed

- Drop fluentd, only use fluent-bit for pushing logs to outputs (fluentd was used for AWS outputs).

### Added

- Add toleration so that it can be run on any nodes with taints

## [v0.5.5]

### Fixed

- Use Docker image with all plugins
- Revert the config path

## v0.5.4

### Fixed

- Use the correct config path for fluentd
- Update the image tag for fluentd

## v0.5.3

### Added

- Added a values.schema.json file to help with validating user values.
- Support AWS role when using Cloudwatch

### Fixed

- Fix whitespace and indententation in deployment

## v0.5.2

### Changed

- Use release date

### Fixed

- Remove extraneous whitespaces

## v0.5.1

### Changed

- Update fluent-bit to v1.4.5

### Fixed

- Fix wrong configuration for elasticsearch

## v0.5.0

### Added

- Add kiam support

## v0.4.0

### Added
- Add syslog support
- Multiple target support
- Add more customization options

### Changed
- Update fluentd to v1.10.2
- Moved Azure Loganalytics and Elasticsearch to fluent-bit

## v0.3.0

### Changed
- Update fluentd to v1.10.1
- Update fluent-bit to v1.4.2

## v0.2.2

### Changed
- Improving log forwarding performance
- Fixing label issues with app and app.kubernetes.io/name

## v0.2.1

### Changed

- Add Elasticsearch support

## v0.2.0

### Changed

- Add Azure Log Analytics support

## v0.1.3

### Changed

- Add Giant Swarm monitoring option

## [v0.1.2]

### Changed

- Add optional parameter `grant_full_control` to allow define permission for the object stored in S3 bucket.
- Changed `s3_object_key_format` to let define the object key format via values file.

## [v0.1.1]

### Changed

- Update chart metadata to show useful data in our UI.

## [v0.1.0]

### Changed

- Add first version of the Fluent Logging App chart based on the community Fluentd and Fluentbit charts.
- Add CloudWatch and S3 plugin in Fluentd as storage backends.


[Unreleased]: https://github.com/giantswarm/fluent-logshipping-app/compare/v5.1.1...HEAD
[5.1.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v5.1.0...v5.1.1
[5.1.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v5.0.0...v5.1.0
[5.0.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v4.2.0...v5.0.0
[4.2.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v4.1.0...v4.2.0
[4.1.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v4.0.0...v4.1.0
[4.0.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v3.1.2...v4.0.0
[3.1.2]: https://github.com/giantswarm/fluent-logshipping-app/compare/v3.1.1...v3.1.2
[3.1.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v3.1.0...v3.1.1
[3.1.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v3.0.2...v3.1.0
[3.0.2]: https://github.com/giantswarm/fluent-logshipping-app/compare/v3.0.1...v3.0.2
[3.0.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v3.0.0...v3.0.1
[3.0.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.3.3...v3.0.0
[2.3.3]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.3.2...v2.3.3
[2.3.2]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.3.1...v2.3.2
[2.3.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.3.0...v2.3.1
[2.3.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.2.0...v2.3.0
[2.2.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.1.0...v2.2.0
[2.1.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.0.3...v2.1.0
[2.0.3]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.0.2...v2.0.3
[2.0.2]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.0.1...v2.0.2
[2.0.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v2.0.0...v2.0.1
[2.0.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v1.4.0...v2.0.0
[1.4.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v1.3.0...v1.4.0
[1.3.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v1.1.1...v1.2.0
[1.1.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v1.0.1...v1.1.0
[1.0.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.7.3...v1.0.0
[0.7.3]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.7.2...v0.7.3
[0.7.2]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.7.1...v0.7.2
[0.7.1]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.7.0...v0.7.1
[0.7.0]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.6.7...v0.7.0
[0.6.7]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.6.6...v0.6.7
[v0.6.6]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.6.6
[v0.6.0]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.6.0
[v0.5.3]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.5.3
[v0.5.2]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.5.2
[v0.5.1]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.5.1
[v0.5.0]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.5.0
[v0.4.0]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.4.0
[v0.3.0]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.3.0
[v0.2.2]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.2.2
[v0.2.1]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.2.1
[v0.2.0]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.2.0
[v0.1.3]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.1.3
[v0.1.2]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.1.2
[v0.1.1]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.1.1
[v0.1.0]: https://github.com/giantswarm/fluent-logshipping-app/releases/tag/v0.1.0
