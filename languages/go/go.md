---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Go
{: #go}

Given its rapidly increasing popularity as a server-side language with strong cross-platform portability, Go support is imperative to increase adoption of your IBM Cloud service.

## Environment support
{: #go-environment-support}

Your Go SDK should support Go releases go1.12 and up.

## Publishing
{: #go-publishing}

All Go SDKs should be publicly available in an [IBM GitHub organization](/docs/sdk-handbook?topic=sdk-handbook-distribution#open-source).

Your SDK should follow the [semantic versioning best practices](/docs/sdk-handbook?topic=sdk-handbook-distribution#semantic-versioning).

## Community support
{: #go-community-support}

Allow your users to find answers to their questions.  Users should be able to report problems on GitHub by raising issues on your SDK repository.  Having a public Slack channel is a great way to engage with users who have questions specific to their use cases.

## Style guidelines
{: #go-style-guidelines}

You should follow the conventions from [Golang "Effective Go" style guide](https://golang.org/doc/effective_go.html).

You should use the standard [development tools](/docs/sdk-handbook?topic=sdk-handbook-developer-tools) for Go to check style and code coverage.

## Streaming support
{: #go-streaming-support}

If your API takes file parameters, you should accept Go file streams (e.g. io.ReadCloser) as an input type.

## Dependencies
{: #go-dependencies}

You should use the standard dependencies provided by Go, like `net/http`, `os`, `strings`, and `fmt` to write your code.

## Objects for arguments
{: #go-objects-for-arguments}

The methods of your SDK that represent operations of your service should take a single argument - an instance of an "options" struct. Each operation should have its own options struct which contains fields that represent the operation parameters.

## Standard features
{: #go-standard-features}

### Authentication
{: #go-authentication}

You are not required to use a particular library to provide the authentication for your service.

Your SDK must support all of the authentication methods supported by your service.

### Configuration
{: #go-configuration}

Your SDK should allow various SDK configuration properties (e.g. service URL, authentication credentials) to be supplied through an external configuration mechanism (e.g. properties file or environment variables) in addition to a programmatic path. This will relieve SDK users from focusing on configuration-related functionality and will allow applications using your SDK to be flexible and avoid 'hard-coding' configuration information inside the application code.

If you build this capability into your SDK, you must document this mechanism clearly with examples.

### Using go-sdk-core

[IBM `go-sdk-core`](https://github.com/IBM/go-sdk-core) provides configuration and authentication support. You can use the existing functionality provided by this dependency in your SDK.


## Documentation
{: #go-documentation}

Your SDK is not useful if your audience cannot understand how to consume it in order to do the basic operations for your service. Your SDK needs to contain the following resources to help your users:

* `README.md`
* [Contributor guidelines](/docs/sdk-handbook?topic=sdk-handbook-documentation#contributor-documentation)
* [API reference documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation#interface-documentation)
* Code Samples
* [Service documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation)

## Samples
{: #go-samples}

For your Go SDK, you will want some simple code samples and explanations of what each does.  Linking out to the API reference documentation for more advanced use is strongly encouraged.

At minimum, the samples should be included in the `README.md` file. They should communicate how to install the library, and complete the basic operations provided by your API.
