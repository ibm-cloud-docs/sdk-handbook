---

copyright:
  years: 2019, 2026
lastupdated: "2026-09-14"

keywords: sdk, coding style, coding conventions, idiomatic style

subcollection: sdk-handbook

---

{{site.data.keyword.attribute-definition-list}}

# Coding style
{: #coding-style}

The SDK coding style defines the conventions and best practices for writing consistent, idiomatic SDK code.
{: shortdesc}

## Coding conventions
{: #coding-style-coding-conventions}

The SDK MUST adhere to coding style that is clearly documented in the SDK CONTRIBUTING file.
The SDK SHOULD adopt the coding style recommendation that is given in the appropriate
language-specific section of these guidelines.

## Idiomatic style
{: #codingstyle-idiomatic-style}

The SDK SHOULD employ the generally accepted best practices and common idioms of the specific language.
The SDK SHOULD feel "natural" to developers with experience in that language.
In particular, the JSON structure of the underlying API request and response structures SHOULD be
converted to native language objects with appropriately typed member variables.

## Use style checkers
{: #codingstyle-checkers}

The SDK SHOULD employ a code style checker to enforce the established coding style.
See [style checkers](/docs/sdk-handbook?topic=sdk-handbook-devtools#devtools-style-checkers).
