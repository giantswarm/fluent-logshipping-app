# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project's packages adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

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


[Unreleased]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.7.0...HEAD
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
