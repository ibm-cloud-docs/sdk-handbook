---

copyright:
  years: 2019
lastupdated: "2020-01-27"

subcollection: sdk-handbook

---

# Distribution

## Open source

The SDK MUST be open source -- hosted on an IBM public GitHub repository.
- Should be discoverable through simple GitHub and Google searches
- Should use the Apache 2.0 license.

## Package management

The SDK SHOULD be distributed using the most common/popular package management systems for the language.
See [package management](/docs/sdk-handbook?topic=sdk-handbook-developer-tools#package-management) for the recommended package managers by language and their respective requirements.

## Package dependencies

The SDK should use the common dependency management system for declaring its dependencies,
including "lock" files wherever supported to specify the actual versions of dependencies used when creating an SDK release.
Dependency versions should be specified with a fixed major version to avoid incompatible changes
that may occur in major version updates.

## Semantic versioning

The SDK MUST use [semantic versioning](https://semver.org/) for SDK releases
(this requirement is enforced by some package management systems).
