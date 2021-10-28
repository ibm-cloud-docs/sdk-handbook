---

copyright:
  years: 2020, 2021
lastupdated: "2021-10-27"

subcollection: sdk-handbook

---

# Swift
{: #swift}

As stated in the [general SDK Guidelines](/docs/sdk-handbook?topic=sdk-handbook-intro), the SDK should make it easy for application developers to access your API in their preferred language. Given its adoption by Apple developers, providing a Swift SDK will allow iOS, macOS, and even server-side applications to leverage the capabilities of your service API in their applications.

## Environment support
{: #swift-environment-support}

Your Swift SDK should support the latest major release of Swift, in order to ensure compatibility with developers using Xcode.

To increase adoption of the SDK, it should be compatible in all Swift environments:
* tvOS
* iOS
* macOS
* watchOS
* Linux systems, for backend server-side Swift projects

If your SDK does not support one of these for specific operations, you must use the proper annotations so that developers can work around these limitations when incorporating the SDK into their Xcode projects.

### Objective-C compatibility
{: #swift-objective-c-compatibility}

Given the goal of Swift to be a self-sufficient language, Objective-C compatibility does not necessarily need to be maintained.  Some SDK service teams may opt to include this as part of their SDK where merited. If consumption by Objective-C applications is important for your service, providing reference material describing how to construct a [custom bridge](https://watson-developer-cloud.github.io/swift-sdk/docs/objective-c) could be beneficial.

## Publishing
{: #swift-publishing}

All Swift SDKs should be publicly available in an [IBM GitHub organization](https://test.cloud.ibm.com/docs/sdk-handbook?topic=sdk-handbook-distribution#open-source). To aid in adoption of your SDK, you should make your SDKs available in all three major package managers in the Swift network, if they are still useful to your target audience.

Your SDK should follow the [semantic versioning best practices](https://test.cloud.ibm.com/docs/sdk-handbook?topic=sdk-handbook-distribution#semantic-versioning).

### Community support
{: #swift-community-support}

Allow your users to find answers to their questions.  Users should be able to report problems on GitHub by raising issues on your SDK repository.  Having a public Slack channel is a great way to engage with users who have questions specific to their use cases.

## Style guidelines
{: #swift-style-guidelines}

You should follow the conventions from [The Official raywenderlich.com Swift Style Guide](https://github.com/raywenderlich/swift-style-guide) and the [Swift API Design Guidelines](https://swift.org/documentation/api-design-guidelines/), with exceptions as follows:

* Use the following style for empty arrays and dictionaries per [The Swift Programming Language](https://docs.swift.org/swift-book/GuidedTour/GuidedTour.html#//apple_ref/doc/uid/TP40014097-CH2-ID461l):    

```swift
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
```

* Use four spaces for indentation
* Maximum 500 characters line width

For an example SDK with these styles, see the [swift-sdk-template](https://github.ibm.com/CloudEngineering/swift-sdk-template).

Given that the overwhelming majority of SDK adopters will be using Xcode as their development environment, you will want to include your `.xcodeproj` directory for contributors to easily get started.

You should use the standard [development tools](/docs/sdk-handbook?topic=sdk-handbook-developer-tools) for Swift to check style and code coverage.


## Standard features
{: #swift-standard-features}

### Authentication
{: #swift-authentication}

You are not required to use a particular library to provide the authentication for your service.

Your SDK must support all of the authentication methods supported by your service.

### Configuration
{: #swift-configuration}

Your SDK should allow various SDK configuration properties (e.g. service URL, authentication credentials) to be supplied through an external configuration mechanism (e.g. properties file or environment variables) in addition to a programmatic path. This will relieve SDK users from focusing on configuration-related functionality and will allow applications using your SDK to be flexible and avoid 'hard-coding' configuration information inside the application code.

If you build this capability into your SDK, you must document this mechanism clearly with examples.

### Requests
{: #swift-requests}

Most networking operations in your Swift SDK should be asynchronous.  `DispatchGroups` and other semaphores can be used for synchronous operations.

### Using swift-sdk-core
{: #swift-core}

[IBM `swift-sdk-core`](https://github.com/IBM/swift-sdk-core), formerly `watson-developer-cloud/RestKit` provides configuration and authentication support. You can use the existing functionality provided by this dependency in your SDK to leverage key capabilities in similar manners across the IBM Cloud.

## Documentation
{: #swift-documentation}

Your SDK is not useful if your audience cannot understand how to consume it in order to do the basic operations for your service. Your SDK needs to contain the following resources to help your users:

* `README.md`
* [Contributor Guidelines](/docs/sdk-handbook?topic=sdk-handbook-documentation#sdk-contributor-docs)
* Code Samples
* [Service documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation)

### Samples
{: #swift-samples}

For your Swift SDK, you will want some simple code samples and explanations of what each does.  Linking out to the API reference documentation for more advanced use is strongly encouraged.

At minimum, the samples should be included in the `README.md` file. They should communicate how to install the library, and complete the basic operations provided by your API.
