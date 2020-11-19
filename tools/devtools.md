---

copyright:
  years: 2020
lastupdated: "2020-01-06"

subcollection: sdk-handbook

---

# Developer tools

## Style checkers

Recommended style checkers are

- Go: [golint](https://github.com/golang/lint)
- Java: [checkstyle](http://checkstyle.sourceforge.net/)
- Node: [eslint](https://eslint.org/)
- Python: [pylint](https://www.pylint.org/)
- Swift: [SwiftLint](https://github.com/realm/SwiftLint)

## Code coverage

Recommended test coverage tools are:

- Go: [cover](https://golang.org/cmd/cover/)
- Java: [jacoco](http://www.jacoco.org/jacoco/trunk/index.html)
- Node: [jest](https://jestjs.io/)
- Python: [coverage](https://pypi.python.org/pypi/coverage)
- Swift: [Codecov](https://codecov.io/)

## Package management / distribution
{: #package-management}

It is highly recommended that individual services belonging to an IBM Cloud service category are delivered together within a single SDK project (one project per language). For example, the services within the Platform Services category are contained within the `platform-services-go-sdk` project.

Recommended package management / distribution systems:

### Node
Your Node SDK should be released as an [npm](https://www.npmjs.com/) package within the [ibm-cloud](https://www.npmjs.com/org/ibm-cloud) organization. It is recommended that your package name follows the pattern of ibm-<service-category> if possible (for example, `ibm-platform-services` or `ibm-networking-services`). Using [NPM Scopes](/docs/sdk-handbook?topic=sdk-handbook-node#node-publishing) is strongly encouraged.

### Go
Your Go SDK should be packaged as a [Go Module](https://blog.golang.org/using-go-modules), using the GitHub repository URL as a package name.

### Java
Your Java SDK should publish its artifacts on [JCenter](https://bintray.com/bintray/jcenter) and [Maven Central](https://search.maven.org/).  It is recommended that artifacts use a Maven groupId of `com.ibm.cloud`.

### Python
Your Python SDK should be released on [PyPI](https://pypi.python.org/) / [pip](https://pypi.python.org/pypi/pip) and should have a package name beginning with `ibm-`. It is recommended that your package name follows the pattern of ibm-<service-category> if possible (for example, `ibm-platform-services` or `ibm-networking-services`).

### Swift
Your Swift SDK should be released on [Swift Package Manager](https://swift.org/package-manager/) / [CocoaPods](https://cocoapods.org/) / [Carthage](https://github.com/Carthage/Carthage) and should have a package name beginning with `IBM`.

Additional information is present in the [Common SDK Documentation](https://github.com/IBM/ibm-cloud-sdk-common).
