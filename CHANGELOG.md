# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.2.0] - 2022-07-11

### Changed

- Secrets upgraded to version `external-secrets.io/v1beta1`

## [1.1.0] - 2022-06-30

### Changed

- Added `namespace: external-dns` to [values.yaml](chart/values.yaml) as required by [Karavel CLI 0.4](https://github.com/karavel-io/cli/releases/tag/v0.4.0)
- Updated to [external-dns v0.12.0](https://github.com/kubernetes-sigs/external-dns/releases/tag/v0.12.0)

## [1.0.0] - 2022-03-22

Initial release

[unreleased]: https://github.com/karavel-io/platform-component-external-dns/compare/1.2.0...HEAD
[1.2.0]: https://github.com/karavel-io/platform-component-external-dns/compare/1.1.0...1.2.0
[1.1.0]: https://github.com/karavel-io/platform-component-external-dns/compare/1.0.0...1.1.0
[1.0.0]: https://github.com/karavel-io/platform-component-external-dns/releases/tag/1.0.0
