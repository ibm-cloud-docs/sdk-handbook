---

copyright:
  years: 2019
lastupdated: "2019-11-06"

subcollection: sdk-handbook

---

# Java

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

## Coding style
{: #java-coding-style}

For services that support both a traditional Java SDK and an Android SDK, the Java
SDK SHOULD be designed to be Android compatible, to minimize duplication of code.

### Style checkers
{: #java-style-checkers}

Style guidelines should be enforced using the [checkstyle](http://checkstyle.sourceforge.net/) plugin for Maven or Gradle.

## Documentation
{: #java-documentation}

### Interface documentation
{: #java-interface-documentation}

The SDK MUST provide accompanying Javadoc documentation for all external interfaces.

## Distribution
{: #java-distribution}

### Package management
{: #java-package-management}

Official SDK releases MUST be published in [Maven Central](https://search.maven.org/).
Official and beta/snapshot relesaes SHOULD be published in [Sonatype](https://oss.sonatype.org).

<!-- ## Support  - no Java specific content -->
