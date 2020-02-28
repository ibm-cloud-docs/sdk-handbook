---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Why generate SDKs?

## Leverage code generation

The basic service-level elements of the SDK SHOULD be generated from the API definition.
The reasons for using SDK generation include:

- Faster time to Market: Decrease time from new features available in a service and the SDK support for these features.
- Improved Quality:  Avoid “copy-and-paste” and typo errors that occur in hand-written SDKs.
- Enforce Compliance: Improve/enforce agreement with the API definition.
- Enforce Consistency: Common style for a particular language SDK across a family of APIs.
- Increase Adoption: Generated SDKs have common style making them easier for developers to learn.

## Core SDK Libraries

SDKs produced with generation require a common set of capabilities, such as networking operations or authentication mechanisms.  Handwritten SDKs are also welcome to leverage these common operations.

Core Libraries:

* [IBM `go-sdk-core`](https://github.com/IBM/go-sdk-core)
* [IBM `java-sdk-core`](https://github.com/IBM/java-sdk-core)
* [IBM `node-sdk-core`](https://github.com/IBM/node-sdk-core)
* [IBM `python-sdk-core`](https://github.com/IBM/python-sdk-core)
* [IBM `swift-sdk-core`](https://github.com/IBM/swift-sdk-core)
