---

copyright:
  years: 2019, 2026
lastupdated: "2026-09-14"

keywords: sdk, distribution, open source, package management, semantic versioning

subcollection: sdk-handbook

---

{{site.data.keyword.attribute-definition-list}}

# Distribution
{: #distribution}

These guidelines define how an SDK is published, licensed, and versioned for consumption by developers.
{: shortdesc}

## Open-source
{: #distribution-opensrc}

The SDK MUST be open-source and hosted on a public GitHub repository in the [IBM organization](https://github.com/IBM){: external}. The repository name SHOULD follow the pattern of `<service>-<language>-sdk` (for example, `platform-services-node-sdk`).
The SDK SHOULD be discoverable through simple GitHub and Google searches.
The SDK SHOULD use the Apache 2.0 license.

## Package management
{: #distribution-pkgmgmt}

The SDK SHOULD be distributed using the most popular package management systems for the language.
See [package management](/docs/sdk-handbook?topic=sdk-handbook-devtools#devtools-pkg-mgmt) for the recommended package managers by language and their respective requirements.

## Package dependencies
{: #distribution-pkgdeps}

The SDK SHOULD use the common dependency management system for declaring its dependencies,
including "lock" files wherever supported to specify checksummed versions of dependencies used in an SDK release.
Dependency versions should be specified with a fixed major version to avoid incompatible changes
that might occur in major version updates.

## Semantic versioning
{: #distribution-semver}

The SDK MUST use [semantic versioning](https://semver.org/){: external} for SDK releases
(this requirement is enforced by some package management systems).
