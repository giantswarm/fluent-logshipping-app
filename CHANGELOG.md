# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project's packages adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## Unreleased

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


[Unreleased]: https://github.com/giantswarm/fluent-logshipping-app/compare/v0.5.0...master
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