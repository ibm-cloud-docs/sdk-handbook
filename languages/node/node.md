---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Node

As one of the most popular programming languages in use today, JavaScript support is imperative to increase adoption of your IBM Cloud service.  The great strength of JavaScript is its flexibility; it can be used in backend [Node.js](https://nodejs.org/) applications, as well as in client side frameworks like [React](https://reactjs.org/), [Angular](https://angularjs.org/) and [Vue](https://vuejs.org/), among others.  This introduces special considerations that need to be observed in order to meet the needs of these diverse use cases.

## TypeScript

Your JavaScript library should be written in [TypeScript](https://www.typescriptlang.org/).  This will allow TypeScript applications and JavaScript alike to use your SDK.

## Environment support
{: #node-environment-support}

* All [LTS versions](https://nodejs.org/en/about/releases/) of Node should be supported by your SDK.
* Your SDK should support all TypeScript releases above 3.1.
* All modern browsers should be supported by your SDK.
* Ensure your SDK is compatible with React, Angular, and Vue.

## Publishing
{: #node-publishing}

All Node SDKs should be publicly available on an [IBM GitHub organization](/docs/sdk-handbook?topic=sdk-handbook-distribution#open-source).  The releases of these SDKs should be published on [NPM](https://www.npmjs.com/).

Your SDK should follow the [semantic versioning best practices](/docs/sdk-handbook?topic=sdk-handbook-distribution#semantic-versioning).

## Community support
{: #node-community-support}

Allow your users to find answers to their questions.  Users should be able to report problems on GitHub by raising issues on your SDK repository.  Having a public Slack channel is a great way to engage with users who have questions specific to their use cases.


## Style guidelines
{: #node-style-guidelines}

You should follow the [Airbnb conventions](https://github.com/airbnb/javascript), with two spaces for indentation.

You should use the standard [development tools](/docs/sdk-handbook?topic=sdk-handbook-developer-tools) for JavaScript to check style and code coverage.

## Streaming support
{: #node-streaming-support}

If your API takes fileType parameters, you should accept Node.js streams as an input type.

## Dependencies
{: #node-dependencies}

Use a well-defined, well-documented request library that includes browser support, like [axios](https://github.com/axios/axios), [superagent](https://github.com/visionmedia/superagent), or [node-fetch](https://github.com/node-fetch/node-fetch).

## Objects for arguments
{: #node-objects-for-arguments}

The methods in your SDK should take a JSON object as an argument. This object will contain the options for the requests, instead of using positional parameters in the function definition.

## Async architecture
{: #node-async-architecture}

All network calls from your SDK should be asynchronous. All asynchronous calls should be handled using Promises, not callbacks.


## Standard features
{: #node-standard-features}

## Authentication
{: #node-authentication}

You are not required to use a particular library to provide the authentication for your service.

Your SDK must support all of the authentication methods for your service.

## Configuration
{: #node-configuration}

In the interests of making your SDK easy to consume and cloud native, you should provide the ability to read in environment variables.  Abstracting the application logic from the environment logic allows your users to focus on using your service capabilities their applications.

If you build this capability into your SDK, you must document this mechanism clearly with examples.

## Using node-sdk-core

[IBM `node-sdk-core`](https://github.com/IBM/node-sdk-core) provides configuration and authentication support. You can use the existing functionality provided by this dependency in your SDK.


## Documentation
{: #node-documentation}

Your SDK is not useful if your audience cannot understand how to consume it in order to do the basic operations for your service. Your SDK needs to contain the following resources to help your users:

* `README.md`
* NPM metadata
* [Contributor guidelines](/docs/sdk-handbook?topic=sdk-handbook-coding-style#documented-in-contributing)
* [API reference documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation#interface-documentation)
* [TypeDoc documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation#interface-documentation)
* Code Samples
* [Service documentation](/docs/sdk-handbook?topic=sdk-handbook-documentation)

## Samples
{: #node-samples}

For your JavaScript SDK, you will want some simple code samples and explanations of what each does.  Linking out to the API reference documentation for more advanced use is strongly encouraged.

At minimum, the samples should be included in the `README.md` file. They should communicate how to install the library, and complete the basic operations provided by your API.

The samples should include JavaScript and TypeScript examples where applicable as well as simple installation and initialization instructions for Angular and React.
