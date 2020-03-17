# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project's packages adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## v0.2.2

### Added
- Improving log forwarding performance
- Fixing label issues with app and app.kubernetes.io/name

## v0.2.1

### Added

- Add Elasticsearch support

## v0.2.0 

### Added

- Add Azure Log Analytics support

## v0.1.3 

### Added

- Add Giant Swarm monitoring option

## [v0.1.2] 

### Added

- Add optional parameter `grant_full_control` to allow define permission for the object stored in S3 bucket.
- Changed `s3_object_key_format` to let define the object key format via values file.

## [v0.1.1] 

### Updated

- Update chart metadata to show useful data in our UI.

## [v0.1.0] 

### Added

- Add first version of the Fluent Logging App chart based on the community Fluentd and Fluentbit charts.
- Add CloudWatch and S3 plugin in Fluentd as storage backends. 
