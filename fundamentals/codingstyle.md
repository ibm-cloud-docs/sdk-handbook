---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Coding style

## Coding style

The SDK MUST adhere to coding style that is clearly documented in the SDK CONTRIBUTING file.
The SDK SHOULD adopt the coding style recommendation given in the appropriate
language-specific section of these guidelines.

## Idiomatic style

The SDK SHOULD employ the generally accepted best practices and common idioms of the specific language.
The SDK SHOULD feel "natural" to developers with experience in that language.
In particular, the JSON structure of the underlying API request and response structures SHOULD be
converted to native language objects with appropriately typed member variables.

## Use style checkers

The SDK SHOULD employ a code style checker to enforce the established coding style.
See [style checkers](/docs/sdk-handbook?topic=sdk-handbook-developer-tools#style-checkers).
