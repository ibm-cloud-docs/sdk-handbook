---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Content

## Languages / platforms

Every IBM Service that offers public APIs SHOULD offer SDKs for the languages / platforms
most commonly used by developers that use the service.
- Java, Node, Python, and Go are "first-tier" languages that should have SDK support.
- iOS and Android SDKs are important for services that may be used from mobile devices.
- Other languages that may warrant SDK support in particular domains are C#, Ruby, Scala.

## Basic interface

The SDK SHOULD provide a basic interface that maps directly onto the operations of the underlying API.
Each method of an SDK SHOULD correspond to exactly one operation of the underlying API, and
this relationship should be clear from design of the API.

Operations whose functionality is fully supported by a related operation SHOULD be omitted.
This can occur, for example, when an operation is exposed with both a `GET` and an `POST` method,
where the `GET` offers a subset of the features of the `POST` but with a simpler interface.

## Methods

Methods MUST employ a flexible parameter-passing design that allows optional parameters to be added
to a method without causing incompatibility with applications using the prior version of the method.

In some languages this can be accomplished using standard language features like default parameter values,
but in other languages (e.g. Java) the method parameters must be encapsulated into an "options" object.

## Request and response headers

SDK methods MUST allow custom request headers to be provided that are added to the API request, and
MUST provide a means to access the headers returned in the API response[^design-philosophy].

## Streaming

For a language/runtime that supports stream value types:
- The SDK SHOULD allow any potentially large input value to a method to be supplied as a stream.
- The SDK SHOULD allow the result of a method to be returned as a stream if that value may be large.

## Asynchronous method calls

The SDK MUST support asynchronous invocation of any method that performs a network operation.
The SDK SHOULD support synchronous or pseudo-synchronous (e.g. async/await) invocation of methods
that perform network operation in languages where this method style is idiomatic.

## Instrumentation

The SDK SHOULD be instrumented so that relevant usage data can be collected by the service.
In particular, the SDK should supply the SDK name and version in the `User-Agent` header of each API request,
along with supporting information such as language version, OS name and version, etc. whenever
such information is readily available.

## Parameter validation

The SDK MUST perform basic validation of method parameters and
return errors/exceptions _before_ invoking the underlying API.
For example, the SDK should ensure all required parameters have been supplied before invoking the API.

However, validation of specific enum values SHOULD NOT be performed in the SDK, since this would preclude
the SDK from being used with a later version of the service that supports new enum values for a parameter.

## Default values

The SDK SHOULD NOT supply default values for any parameter not supplied by the caller, even if a default
value is clearly specified in the API documentation.  Rather, the assignment of the default should be
delegated to the service, so that the service can alter the default value when appropriate without
impacting the SDK.

## Serialization and deserialization

The SDK MUST silently ignore additional properties in response payloads,
to allow the SDK to work with newer versions of the service.

The SDK SHOULD silently ignore additional properties in dictionary- or map-type parameters.
This is to allow values that may have been returned from a newer version of the service to
be supplied on subsequent method invocations.

## Retry

The SDK MAY provide an automated retry mechanism provided that the user can specify:
- The maximum number of retry attempts, including zero.
- The minimum and maximum time interval between retry attempts.
- The HTTP status codes or error classes that should be retried.

The retry mechanism should respect a "retry-after" response header if one is returned from the service.

## Logging

The SDK MAY provide a logging mechanism provided that the user can specify a logging level, such as "error",
"warning", "informational", or "verbose" that determines the frequency and volume of log entries.

The SDK logging mechanism SHOULD employ the common logging framework for the language.

## Centralize common features

The SDK SHOULD minimize the developer burden for common tasks such as authentication,
and expose service versioning in a highly consumable fashion.
In particular, these aspects are generally best provided as methods on a _client object_
rather than being exposed on each method of the SDK.

## Tests

The SDK SHOULD include both unit and integration tests.
The SDK SHOULD use a test coverage tool to measure code coverage and
establish a coverage target (recommended > 80%) to be achieved for SDK releases.
See [code coverage](/docs/sdk-handbook?topic=sdk-handbook-developer-tools#code-coverage).

<!-- --------------------------------------------------------------------------- -->

[^design-philosophy]: The design philosophy behind many of these guidelines is to ensure that the SDK expose the full set of capabilities available in the underlying API. This is to avoid the need to bypass the SDK and implement directly to the API because the SDK does not support some API feature.
