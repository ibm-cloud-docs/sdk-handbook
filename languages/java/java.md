---

copyright:
  years: 2019, 2021
lastupdated: "2021-10-25"

subcollection: sdk-handbook

---

# Java
{: #java}

As a standard bearer for enterprise application development and the native application language for
Android, Java is a key language to support for your IBM Cloud service.   

## Content
{: #java-content}

### Methods
{: #java-methods}

Method parameters MUST be encapsulated into an “options” object that can be constructed with a "Builder".

### Streaming
{: #java-streaming}

The SDK SHOULD accept parameters with potentially large memory requirements as `InputStream` values,
to allow the value to be streamed to the service.

<!-- ## Naming - no Java specific content -->

<!-- ## Errors - no Java specific content -->

<!-- ## Pagination - no Java specific content -->

## Style guidelines
{: #java-style-guidelines}

For services that support both a traditional Java SDK and an Android SDK, the Java
SDK SHOULD be designed to be Android compatible, to minimize duplication of code.

You should follow a coding style based on the [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html).

You should use the standard [development tools](/docs/sdk-handbook?topic=sdk-handbook-developer-tools) for Java to check style and code coverage.

## Documentation
{: #java-documentation}

### Interface documentation
{: #java-interface-documentation}

The SDK SHOULD provide accompanying Javadoc documentation for all external interfaces.

## Distribution
{: #java-distribution}

### Package management
{: #java-package-management}

Official SDK releases MUST be published in [Maven Central](https://search.maven.org/).

<!-- ## Support  - no Java specific content -->
