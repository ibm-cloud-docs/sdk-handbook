---

copyright:
  years: 2019, 2024
lastupdated: "2024-07-15"

subcollection: sdk-handbook

---

# Why generate SDKs?
{: #sdkgen}

## Leverage code generation
{: #sdkgen-leverage-codegen}

The basic service-level elements of the SDK SHOULD be generated from the API definition.

The reasons for using SDK generation include:

- Faster time to market. Reduce the time it takes to add SDK support for new features in a service.
- Improved quality. Avoid “copy-and-paste” and typo errors that occur in hand-written SDKs.
- Enforced compliance. Improve and enforce agreement with the API definition.
- Enforced consistency. Establish a common style for a particular language SDK across a family of APIs.
- Increased adoption. Generated SDKs have common style, making them easier for developers to learn.

## Core SDK libraries
{: #sdkgen-core-libs}

SDKs produced with generation require a common set of capabilities, such as networking operations or authentication mechanisms.  Handwritten SDKs are also welcome to leverage these common operations.

Core libraries:

* [IBM `go-sdk-core`](https://github.com/IBM/go-sdk-core)
* [IBM `java-sdk-core`](https://github.com/IBM/java-sdk-core)
* [IBM `node-sdk-core`](https://github.com/IBM/node-sdk-core)
* [IBM `python-sdk-core`](https://github.com/IBM/python-sdk-core)
